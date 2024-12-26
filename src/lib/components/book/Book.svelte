<script lang="ts">
    import BookPage from "./BookPage.svelte";

    interface BookType {
        imgUrls: string[];
        index?: number;
        singlePageMode?: boolean;
        backUrl?: string;
    }

    interface Page {
        frontPage: string;
        backPage?: string;
        index: number;
    }

    let {
        imgUrls,
        index = $bindable(0),
        backUrl = "",
        singlePageMode = false,
    }: BookType = $props();

    let pages: Page[] = $derived.by(() => {
        if (singlePageMode) {
            return imgUrls.map((item, index) => ({
                frontPage: item,
                backPage: backUrl,
                index: index,
            }));
        }

        const out: Page[] = [];

        for (let i = 0; i < Math.ceil(imgUrls.length / 2); i++) {
            out.push({
                frontPage: imgUrls[i * 2],
                backPage: imgUrls[i * 2 + 1], // will be undefined if out of bound.,
                index: i,
            });
        }

        return out;
    });

    let prevUrl: string | undefined = $state();
    let nextUrl: string | undefined = $state(pages[0].frontPage);

    let transitionPage: Page | undefined = $state();

    const transitionTime = 1000;
    function _nextPage() {
        if (transitionPage) {
            return; // block transition if there already one.
        }

        const nextPage = pages[index + 1];
        nextUrl = nextPage ? nextPage.frontPage : undefined;

        // start transition
        transitionPage = pages[index];

        index += 1; // trigger flip animation

        setTimeout(() => {
            prevUrl = transitionPage?.backPage;
            transitionPage = undefined;
        }, transitionTime);
    }

    function _prevPage() {
        if (transitionPage) {
            return; // block transition if there already one.
        }

        const prevPage = pages[index - 2];
        prevUrl = prevPage ? prevPage.backPage : undefined;
        transitionPage = pages[index - 1];
        index -= 1;

        setTimeout(() => {
            nextUrl = transitionPage?.frontPage;
            transitionPage = undefined;
        }, transitionTime);
    }

    export function nextPage() {
        if (index === pages.length - 1) {
            return;
        }

        _nextPage();
    }
    export function prevPage() {
        if (index === 0) {
            return;
        }

        _prevPage();
    }

    let angle = singlePageMode? 0:10;

    // Some maths to compensate book size after 3d transform, guessed a bit to avoid proper matrix math
    // https://en.wikipedia.org/wiki/3D_projection#Diagram
    let rootwidth = $state(0);
    let rootHeight = $state(0);
    let rotateAmt = $derived((Math.sin((angle * Math.PI) / 180) * (rootHeight + 650)) / 2); // 400 is a guessed value to compensate for 5degree page rotate and margin.

    // scale to shrink by to still fit in original content box even after per 3d transform
    let perspectiveScaleRatio = $derived(1 / (900 / (900 - rotateAmt)));
</script>

<svelte:head>
    {#if imgUrls.length > 0}
        <link rel="preload" href={imgUrls[0]} as="image" fetchpriority="high" />
    {/if}

    {#if index + 1 < imgUrls.length}
        <link rel="preload" href={imgUrls[index + 1]} as="image" />
    {/if}
</svelte:head>

<div
    class="bookRoot"
    bind:clientWidth={rootwidth}
    bind:clientHeight={rootHeight}
        
    style="scale:{perspectiveScaleRatio}; transform: perspective(900px) rotateX({angle}deg);"
>
    <BookPage
        frontUrl={transitionPage ? transitionPage.frontPage : ""}
        backUrl={transitionPage ? (transitionPage.backPage ?? backUrl) : ""}
        {index}
        animationTime={transitionTime}
        {singlePageMode}
    ></BookPage>

    <div
        class="page prev"
        onclick={prevPage}
        onkeydown={(e) => {
            if (e.key === "space" || e.key === "enter") prevPage();
        }}
        role="button"
        tabindex="0"
    >
        <img class:noUrl={prevUrl === undefined} src={prevUrl ?? backUrl} alt="" />
    </div>
    <div
        class="page next"
        onclick={nextPage}
        onkeydown={(e) => {
            if (e.key === "space" || e.key === "enter") nextPage();
        }}
        role="button"
        tabindex="0"
    >
        <img class:noUrl={nextUrl === undefined} src={nextUrl ?? backUrl} alt="" />
    </div>
</div>

<style>
    .bookRoot {
        position: relative;
        width: 100%;
        height: fit-content;

        transform-style: preserve-3d;

        display: flex;

        scale: 0.91;
    }

    .noUrl {
        opacity: 0;
    }

    .page {
        position: relative;
        height: auto;
        width: 50%;
        --coverMargin: 5px;

        transform-style: preserve-3d;
        perspective: 900px;

        transform-origin: right;
        transform: rotateY(4deg);
    }
    img{
        height: auto;
        width: 100%;
    }

    .next {
        transform-origin: left;
        transform: rotateY(-4deg);
    }

    .page::before,
    .page::after {
        /* book cover */
        content: "";
        background-color: #704d40;

        position: absolute;
        z-index: -1;

        left: calc(-1 * var(--coverMargin));
        top: calc(-1 * var(--coverMargin));

        width: calc(100% + var(--coverMargin));
        height: calc(100% + var(--coverMargin) * 2);

        border-radius: 5px;
    }

    /* ::after is to add thickness to cover */
    .page::after {
        background-color: #51362d;
        z-index: -2;
        transform: translate3d(0, 5px, -8px);
    }

    .next::before,
    .next::after {
        left: 0;
    }
</style>
