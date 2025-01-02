<script lang="ts">
  import DesktopNav from "./DesktopNav.svelte";
  import MobileNav from "./MobileNav.svelte";

  let innerWidth = $state(0);
</script>

<svelte:window bind:innerWidth />

{#if innerWidth < 560}
  <MobileNav></MobileNav>
{:else}
  <DesktopNav></DesktopNav>
{/if}
