<script lang="ts">
    import Book from "$lib/components/book/Book.svelte";

    let imgUrls = [...Array(7).keys()].map((idx) => `/bookpages/${idx + 1}.webp`);
</script>

<div class="bleh">
    <Book backUrl={"bookpages/0.webp"} {imgUrls} singlePageMode={true}></Book>
</div>

<style>
    .bleh {
        position: relative;
        min-width: 400px;
        height: auto;
        display: block;

        overflow: hidden;
        resize: both;
        border: 2px solid brown;

        padding: 5rem;
    }
</style>
