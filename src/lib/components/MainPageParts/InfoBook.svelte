<script lang="ts">
  import Book from "$lib/components/book/Book.svelte";
  import StickyLabel from "../StickyLabel.svelte";
  const imgUrls = [...Array(6).keys()].map(
    (idx) => `/bookpages/${idx+1}.webp`
  );
  const backPageUrl = "/bookpages/0.webp";

  let screenWidth = $state(0);
</script>

<div id="our_team" class="bookContainer" bind:clientWidth={screenWidth}>
  <div class="bookHolder">
    <div class="labelContainer"><StickyLabel>THE CHEFS</StickyLabel></div>
    <Book backUrl={backPageUrl} {imgUrls} singlePageMode={screenWidth < 1000}
    ></Book>
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

  @media (max-width: 600px) {
    .bookContainer {
      padding: 1rem;
    }
  }

  .bookHolder {
    max-width: 1800px;

    margin-left: auto;
    margin-right: auto;
  }
</style>
