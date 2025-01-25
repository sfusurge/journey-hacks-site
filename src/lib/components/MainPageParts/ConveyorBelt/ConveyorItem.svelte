<script lang="ts">
  import { onMount } from "svelte";

  interface Props {
    url: string;
    id: number;
    width: number;
  }

  let { url, id, width }: Props = $props();

  let startScroll = $state(false);
  onMount(() => {
    setTimeout(() => {
      startScroll = true;
    }),
      100;
  });
  let bites = $state(-1);
</script>

<!-- svelte-ignore a11y_click_events_have_key_events -->
<!-- svelte-ignore a11y_no_static_element_interactions -->
<div
  class="imgHolder m-scroll"
  style=" --conveyorWidth:{-width}px;"
  class:translated={startScroll}
  onclick={() => {
    bites++;
  }}
>
  <img src={url} alt="bleh" style="mask-image: url('#full'), url('#0{id}');" />

  <svg width="0" height="0">
    <defs>
      <mask id="full" width="300px" height="300px">
        <rect x="0" y="0" width="300px" height="300px" fill="#ffffffff"></rect>
      </mask>

      <mask id="0{id}" width="300px" height="300px">
        {#if bites >= 0}
          <circle cx="30" cy="0" r="60px" fill="#ffffffff"></circle>
        {/if}

        {#if bites >= 1}
          <circle cx="120" cy="30" r="60px" fill="#ffffffff"></circle>
        {/if}

        {#if bites >= 2}
          <circle cx="40" cy="50" r="60px" fill="#ffffffff"></circle>
        {/if}

        {#if bites >= 3}
          <circle cx="40" cy="80" r="70px" fill="#ffffffff"></circle>
        {/if}

        {#if bites >= 4}
          <circle cx="150" cy="80" r="170px" fill="#ffffffff"></circle>
        {/if}
      </mask></defs
    >
  </svg>
</div>

<style>
  img {
    mask-composite: subtract;
    mask-type: alpha;
    pointer-events: none;
  }

  .imgHolder {
    position: relative;
    cursor: pointer;
  }

  .bite {
    position: absolute;
    width: 110px;
    height: 110px;

    border-radius: 50%;
    border: 2px solid red;
    z-index: 20;
    pointer-events: none;

    backdrop-filter: opacity(0);
  }

  .m-scroll {
    position: absolute;
    left: 100%;
    top: 0;
    width: 11.1656%;
    min-width: 100px;
    height: auto;

    transform: translateX(0);
    transition: transform 10s linear;
  }

  .translated {
    transform: translateX(calc(var(--conveyorWidth) - 100%));
  }
</style>
