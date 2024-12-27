<script lang="ts">
    import Book from "$lib/components/book/Book.svelte";
    const imgUrls = [...Array(7).keys()].map((idx) => `/bookpages/${idx + 1}.webp`);
    const backPageUrl = "/bookpages/0.webp";

    let screenWidth = $state(0);
</script>

<div class="bookContainer" bind:clientWidth={screenWidth}>
    <Book backUrl={backPageUrl} {imgUrls} singlePageMode={screenWidth < 1200}></Book>
</div>

<style>
    .bookContainer {
        width: 100%;
        height: fit-content;
        padding: 2rem;

        background-color: #DFB19B;
    }
</style>
