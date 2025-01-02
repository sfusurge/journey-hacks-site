<script lang="ts">
    import { pushState } from "$app/navigation";
    import { page } from "$app/state";

    let defaultNav: string = "bg-[#c4d086]";
    let dockedNav: string = "bg-[#57392E]";

    let scrollY = $state(0);
    let isOpen = $derived(page.state.showModel);
    let navHeight = $state(0);

    let { links }: { links: [string, string][] } = $props();

    function showModel() {
        pushState("", {
            showModel: true,
        });
    }
</script>

<svelte:window bind:scrollY />

<nav
    id="mobile-nav"
    class={`w-screen fixed top-0 left-0 z-[999] transition-colors ${scrollY <= 720 ? defaultNav : dockedNav}`}
>
    <div class={`w-full p-4 flex justify-between`}>
        <button
            class="w-10 h-10 flex items-center"
            aria-label={isOpen ? "Close menu" : "Open menu"}
            onclick={() => {
                if (!page.state.showModel) {
                    showModel();
                } else {
                    history.back();
                }
            }}
        >
            <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="2"
                stroke="currentColor"
                class={`w-7 h-7 mx-auto hover:scale-125 transition ${scrollY <= 720 ? "text-[#57392E]" : "text-white"}`}
            >
                {#if !isOpen}
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
                    ></path>
                {:else}
                    <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12"></path>
                {/if}
            </svg>
        </button>

        <a
            href="https://sfusurge.com/"
            class="w-10 h-10 flex items-center right-4"
            aria-label="SFU Surge"
            target="_blank"
            style="margin-right:10px;"
        >
            <svg
                width="30"
                height="31"
                class="h-8 mx-auto hover:scale-125 transition-colors"
                viewBox="0 0 30 31"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
            >
                <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M14.9695 30.9268C23.2369 30.9268 29.939 24.2247 29.939 15.9573C29.939 7.68986 23.2369 0.987793 14.9695 0.987793C6.70207 0.987793 0 7.68986 0 15.9573C0 24.2247 6.70207 30.9268 14.9695 30.9268ZM10.6408 17.0278L15.8901 3.58291L19.9408 10.4885L14.8445 14.066L17.3959 17.2498L19.9471 20.4338L11.83 26.657L14.2999 18.3678L10.6408 17.0278Z"
                    fill={scrollY <= 720 ? "#57392E" : `#FFFFFF`}
                ></path>
            </svg>
        </a>
    </div>

    <div
        id="links"
        class="relative overflow-hidden"
        style="max-height: {isOpen ? navHeight : 0}px; height: {navHeight}px"
    >
        <div
            class="flex w-full flex-col items-center gap-4 h-fit px-4 absolute left-0 top-0"
            bind:clientHeight={navHeight}
        >
            {#each links as [name, url]}
                <a
                    href={url}
                    class={`${
                        scrollY <= 720 ? "text-[#57392E] hover:text-[#1A672B]" : "text-white hover:text-[#c4d086]"
                    } font-medium text-lg`}>{name}</a
                >
            {/each}
            <a
                href="#"
                class={`${scrollY <= 720 ? "bg-[#57392E] hover:bg-[#231813] hover:text-[#CE9788] text-white" : "bg-[#c4d086] hover:bg-[#d0d99e] text-[#57392E]"} -mt-1 text-lg text-center font-medium w-fit px-6 py-2 rounded-md`}
                >Apply</a
            >
            <div class="h-4 w-full"></div>
        </div>
    </div>
</nav>

<button
    class="w-full h-full fixed top-0 left-0 z-[998] bg-black/60 {isOpen ? 'visible' : 'hidden'}"
    onclick={() => {
        history.back();
    }}
    aria-label="Close the nav if click outside"
></button>

<style>
    #links {
        transition-property: all;
        transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
        transition-duration: 300ms;
    }
</style>
