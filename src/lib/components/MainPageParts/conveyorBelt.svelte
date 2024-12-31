<script lang="ts">
  const imageUrls = [
    // TODO switch to .svg later.
    "food-0.png",
    "food-1.png",
    "food-2.png",
    "food-3.png",
    "food-4.png",
    "food-5.png",
    "food-6.png",
    "food-7.png",
    "food-8.png",
  ];

  let shownImages: { url: string; imgId: number }[] = $state([]);
  let imgIdx = $state(0); //id of the images in the each loop

  const maxCount = 10;
  function addImages() {
    if (Math.random() < 0.2) {
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
    setInterval(addImages, 2000);
  });
</script>

<div
  class="relative w-full h-full max-w-[100vw] -mt-[1px] pointer-events-none select-none"
>
  <img
    alt="background with ledge"
    src="/conveyor-belt/background-with-ledge.png"
    class="relative w-full h-auto"
  />

  <div class="absolute top-0 left-0 w-full h-full">
    <img
      alt="foreground"
      src="/conveyor-belt/foreground.png"
      class="relative w-full h-auto top-[49.3902%] z-30"
    />

    <div
      class="scroll absolute top-[5.8%] z-50 overflow-hidden h-full"
      style=" width: 100%; max-width: 100dvw;"
    >
      {#each shownImages as foodInfo (foodInfo.imgId)}
        <img
          src="/conveyor-belt/{foodInfo.url}"
          alt="bleh"
          class="m-scroll w-[11.1656%] h-auto"
        />
      {/each}
    </div>

    <img
      alt="ledge"
      src="/conveyor-belt/ledge.png"
      class="absolute bottom-0 w-full h-auto auto z-40"
    />

    <img
      alt="background"
      src="/conveyor-belt/background.png"
      class="absolute top-[29.0650%] w-full h-auto auto z-0"
    />

    <img
      alt="wheel 1"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[2.679%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 2"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[16.2520%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 3"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[29.825%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 4"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[43.3984%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 5"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[50.728%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 6"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[64.301%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 7"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[77.8739%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />

    <img
      alt="wheel 8"
      src="/conveyor-belt/wheel-2.png"
      class="absolute left-[91.44689%] top-[41.4674%] w-[5.834%] h-auto auto z-20 animate-spin"
    />
  </div>
</div>

<style>
  .m-scroll {
    animation: scroll 10s linear infinite;
    position: absolute;
    left: 100%;
    top: 0;
  }

  @keyframes scroll {
    from {
      transform: translateX(0);
    }
    to {
      transform: translateX(calc(-100dvw - 100%));
    }
  }
</style>
