<!-- <div class="bg-[#754f4f] relative w-screen max-w-screen min-h-40 h-[30vh]">
  <div
    class="scroller bg-[#754f4f] min-w-[100vw] max-w-[100vw]"
    data-direction="right"
    data-speed="slow"
  ></div>

  <div>
    <img
      id="wheel-1"
      alt="wheel 1"
      src="/conveyor-belt/wheel-2.png"
      class="absolute origin-bottom w-[5.834%] h-auto left-[2.679%] bottom-[32%] z-10"
    />

    <img
      alt="background"
      src="/conveyor-belt/background.png"
      class="absolute origin-bottom bottom-[19.335%] w-full h-auto z-0"
    />

    <img
      alt="foreground"
      src="/conveyor-belt/foreground.png"
      class="absolute origin-bottom w-full h-auto bottom-[19.335%] z-30"
    />
  </div>

  <div
    class="bg-[url('/conveyor-belt/ledge.png')] origin-bottom absolute bottom-0 h-[19.335%] max-h-[109px] object-cover w-screen max-w-screen min-w-screen bg-bottom pointer-events-none"
  ></div>
</div> -->

<div class="h-8 w-full bg-[#754f4f]"></div>

<div class="relative w-full h-full max-w-[100vw]">
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
      class="scroll absolute top-[5.8%] z-50 w-screen max-w-[100vw] overflow-hidden"
    >
      <div class="m-scroll flex gap-[4%]">
        <img
          alt="food 0"
          src="/conveyor-belt/food-0.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 1"
          src="/conveyor-belt/food-1.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 2"
          src="/conveyor-belt/food-2.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 3"
          src="/conveyor-belt/food-3.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 4"
          src="/conveyor-belt/food-4.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 5"
          src="/conveyor-belt/food-5.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 6"
          src="/conveyor-belt/food-6.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 7"
          src="/conveyor-belt/food-7.png"
          class="w-[11.1656%] h-auto"
        />

        <img
          alt="food 8"
          src="/conveyor-belt/food-8.png"
          class="w-[11.1656%] h-auto"
        />
      </div>
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
    animation: scroll 15s linear infinite;
  }

  @keyframes scroll {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-100%);
    }
  }
</style>
