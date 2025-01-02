<script lang="ts">
  import ConveyorItem from "./ConveyorItem.svelte";

  const imageUrls = [
    // TODO switch to .svg later.
    "food-0.webp",
    "food-1.webp",
    "food-2.webp",
    "food-3.webp",
    "food-4.webp",
    "food-5.webp",
    "food-6.webp",
    "food-7.webp",
    "food-8.webp",
    "food-9.webp",
    "food-10.webp",
  ];

  let shownImages: { url: string; imgId: number }[] = $state([]);
  let imgIdx = $state(0); //id of the images in the each loop

  const maxCount = 10;
  function addImages() {
    if (Math.random() < 0.6) {
      return;
    }

    if (shownImages.length < maxCount) {
      shownImages.push({
        url: imageUrls[Math.floor(Math.random() * imageUrls.length)],
        imgId: imgIdx,
      });

      setTimeout(() => {
        shownImages.shift();
      }, 10000);

      imgIdx++;
    }
  }

  $effect(() => {
    /**
     * in react you would do useEffect(()=>{...}, []); (empty dependency array means only run once onMount)
     */
    setInterval(addImages, 1100);
  });
</script>

<div class="relative w-full h-full max-w-[100vw] -mt-[1px]">
  <img
    alt="background with ledge"
    src="/conveyor-belt/background-with-ledge.webp"
    class="relative w-full h-auto"
  />

  <div class="absolute top-0 left-0 w-full h-full">
    <img
      alt="foreground"
      src="/conveyor-belt/foreground.webp"
      class="relative w-full h-auto top-[49.3902%] z-30"
    />

    <div
      class="scroll absolute top-[5.8%] z-50 overflow-hidden h-full"
      style=" width: 100%; max-width: 100dvw;"
    >
      {#each shownImages as foodInfo (foodInfo.imgId)}
        <ConveyorItem url={`/conveyor-belt/${foodInfo.url}`} id={foodInfo.imgId}
        ></ConveyorItem>
      {/each}
    </div>

    <img
      alt="ledge"
      src="/conveyor-belt/ledge.webp"
      class="absolute bottom-0 w-full h-auto auto z-40"
    />

    <img
      alt="background"
      src="/conveyor-belt/background.webp"
      class="absolute top-[29.0650%] w-full h-auto auto z-0"
    />

    <img
      alt="wheel 1"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[2.679%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 2"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[16.2520%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 3"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[29.825%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 4"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[43.3984%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 5"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[50.728%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 6"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[64.301%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 7"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[77.8739%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 8"
      src="/conveyor-belt/wheel-2.webp"
      class="absolute left-[91.44689%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />
  </div>
</div>

<style>
  img {
    animation-direction: reverse;
  }
</style>
