<script lang="ts">
    import Book from "$lib/components/book/Book.svelte";

    let imgUrls = [...Array(7).keys()].map((idx) => `/bookpages/${idx + 1}.webp`);
</script>

<div class="container">
    <Book backUrl={"bookpages/0.webp"} {imgUrls} singlePageMode={false}></Book>
</div>

<style>
    .container {
        position: relative;
        min-width: 400px;
        height: auto;
        display: block;

        overflow: hidden;
        resize: both;
        border: 2px solid brown;
    }
</style>
