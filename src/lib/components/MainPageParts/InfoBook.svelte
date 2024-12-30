<script lang="ts">
    import Book from "$lib/components/book/Book.svelte";
    import StickyLabel from "../StickyLabel.svelte";
    const imgUrls = [1, 3, 5, 7, 11, 13, 15].map((idx) => `/bookpages/${idx }.webp`);
    const backPageUrl = "/bookpages/0.webp";

    let screenWidth = $state(0);
</script>

<div class="bookContainer" bind:clientWidth={screenWidth}>
    <div class="bookHolder">
        <div class="labelContainer"><StickyLabel>THE CHEFS</StickyLabel></div>
        <Book backUrl={backPageUrl} {imgUrls} singlePageMode={screenWidth < 1000}></Book>
    </div>
</div>

<style>
    .bookContainer {
        position: relative;
        z-index: 100;
        width: 100%;
        height: fit-content;
        padding: 2rem;

        background-color: #dfb19b;
    }

    .bookHolder {
        max-width: 1800px;

        margin-left: auto;
        margin-right: auto;
    }
</style>
