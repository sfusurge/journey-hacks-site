<script lang="ts">
    import { page } from "$app/stores";
    import FlexibleBookPage from "./FlexibleBookPage.svelte";

    interface BookType {
        imgUrls: string[];
        index?: number;
        singlePageMode?: boolean;
    }

    interface Page {
        frontPage: string;
        backPage?: string;
        index: number;
    }

    let { imgUrls, index = $bindable(0), singlePageMode = false }: BookType = $props();

    let pages: Page[] = $derived.by(() => {
        if (singlePageMode) {
            return imgUrls.map((item, index) => ({
                frontPage: item,
                backPage: undefined,
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
    export function nextPage() {
        // if (transitionPage) {
        //     return; // block transition if there already one.
        // }

        const nextPage = pages[index + 1];
        nextUrl = nextPage ? nextPage.frontPage : "";

        // start transition
        transitionPage = pages[index];

        index += 1; // trigger flip animation

        setTimeout(() => {
            prevUrl = transitionPage?.backPage;
            // transitionPage = undefined;
        }, transitionTime );
    }

    export function prevPage() {
        // if (transitionPage) {
        //     return; // block transition if there already one.
        // }

        const prevPage = pages[index -2];
        prevUrl = prevPage ? prevPage.backPage : "";
        transitionPage = pages[index - 1 ];
        index -= 1;

        setTimeout(() => {
            nextUrl = transitionPage?.frontPage;
            // transitionPage = undefined;
        }, transitionTime );
    }
</script>

<div class="bookRoot">
    <FlexibleBookPage
        frontUrl={transitionPage ? transitionPage.frontPage : ""}
        backUrl={transitionPage ? (transitionPage.backPage ?? "") : ""}
        {index}
        animationTime={transitionTime}
    ></FlexibleBookPage>

    <div class="prevPage" style="--background: url({prevUrl})"></div>

    <div class="nextPage" style="--background: url({nextUrl})"></div>
</div>

<style>
    .bookRoot {
        position: relative;
        width: 100%;
        height: 100%;

        transform-style: preserve-3d;
        background-color: brown;

        display: flex;

        transform: perspective(1000px) rotateX(25deg);
    }

    .prevPage,
    .nextPage {
        flex: 1;
        background-image: var(--background);
        background-size: 100% 100%;
    }
</style>
