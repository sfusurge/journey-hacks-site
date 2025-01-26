<script>
  let width = $state(0);
</script>

<svelte:window bind:innerWidth={width} />

<svelte:head>
  <link
    rel="preload"
    href="/home-animated/sparky_arm_with_pan.webp"
    as="image"
  />
  <link rel="preload" href="/home-animated/sparky_hand_wave.webp" as="image" />
  <link rel="preload" href="/home-animated/sparky_head_body.webp" as="image" />

  <link rel="preload" href="/home-animated/stormy_hand_wave.webp" as="image" />
  <link rel="preload" href="/home-animated/stormy_head_body.webp" as="image" />

  {#if width < 768}
    <link rel="preload" href="/home-animated/mobile-bg.webp" as="image" />
    <link rel="preload" href="/home-animated/mobile-fg.webp" as="image" />
  {:else}
    <link rel="preload" href="/home-animated/foreground.webp" as="image" />
    <link rel="preload" href="/home-animated/background.webp" as="image" />
  {/if}
</svelte:head>

<div class="max-w-screen overflow-x-hidden">
  <div class="bg-[#c4d086] relative h-40 md:h-24 xl:h-4"></div>

  <div class="relative bg-[#8F6455] aspect-[0.67/1] md:aspect-[1.41/1]">
    <div
      class="title absolute mx-auto w-[100vw] sm:mx-0 sm:right-8 -top-16 md:-top-4 xl:top-16"
    >
      <span class="font-coiny mx-auto sm:mx-0 text-xl lg:text-3xl"
        >FEB 14, 2025</span
      >
      <h1 class="title1 mx-auto sm:mx-0 font-coiny text-5xl">JOURNEY</h1>
      <h1 class="-mt-2 mx-auto sm:mx-0 title2">HACKS</h1>
    </div>

    {#if width < 768}
      <img
        src="/home-animated/mobile-bg.webp"
        alt="background"
        class="w-full h-auto block md:hidden"
      />

      <img
        src="/home-animated/mobile-fg.webp"
        alt="foreground"
        class="w-full h-auto absolute bottom-0 z-[50] block md:hidden"
      />
    {:else}
      <img
        src="/home-animated/background.webp"
        alt="background"
        class="w-full h-auto hidden md:block"
      />
      <img
        src="/home-animated/foreground.webp"
        alt="foreground"
        class="w-full h-auto absolute bottom-0 z-[50] hidden md:block"
      />
    {/if}

    <div
      class="stormy-wobble absolute md:left-[27.39583%] left-[4%] top-[33.1625%] z-20 md:w-[23.8640625%] h-[37.4450951684%] w-[49.69%]"
    >
      <img
        src="/home-animated/stormy_head_body.webp"
        alt="stormy"
        class="absolute w-[75.2962744713%] h-auto z-20"
      />
      <img
        src="/home-animated/stormy_hand_wave.webp"
        alt="stormy's hand"
        class="stormy-hand absolute w-[50.020733%] top-[18.18%] h-auto left-[49.9792662433%] z-10 origin-bottom-left"
      />
    </div>

    <div
      class="sparky-wobble w-[47.608%] md:w-[22.8619791667%] h-[47.9707174231%] absolute left-[48.80208%] top-[22.34407%]"
    >
      <img
        src="/home-animated/sparky_hand_wave.webp"
        alt="sparky's hand"
        class="sparky-hand absolute w-[57.478557456%] h-auto top-[36.7445977292%] z-30 origin-bottom-right"
      />
      <img
        src="/home-animated/sparky_head_body.webp"
        alt="sparky"
        class="absolute w-[72.6638912575%] h-auto right-0 z-40"
      />
    </div>

    <div
      class="sparky-wobble w-[47.608%] md:w-[22.8619791667%] h-[47.9707174231%] absolute left-[46.71875%] top-[22.34407%] z-[60]"
    >
      <img
        src="/home-animated/sparky_arm_with_pan.webp"
        alt="sparky's frying pan"
        class="sparky-pan-hand absolute w-full h-auto left-[8%] top-[56.00524%] origin-[87.025%_20.8%]"
      />

      <img
        src="/home-animated/fish.webp"
        alt="fish"
        class="fish rotate-1 absolute w-[36.6784371796%] z-[40] left-[9.32%] top-[70.5227%] h-auto origin-center"
      />
    </div>
  </div>
</div>

<style>
  /* fish */
  .fish {
    animation: bounce 1s ease-in;
    animation-iteration-count: infinite;
    animation-direction: alternate;
  }

  @keyframes bounce {
    from {
      transform: translateY(-200%);
    }

    to {
      transform: translateY(0%);
    }
  }

  @keyframes fish {
    0% {
      transform: rotate(0deg) translateY(0%);
    }

    25% {
      transform: rotate(20deg) translateY(-300%);
    }

    50% {
      transform: rotate(0deg) translateY(0%);
    }

    75% {
      transform: rotate(-20deg) translateY(-300%);
    }

    100% {
      transform: rotate(0deg) translateY(0%);
    }
  }

  /* sparky pan in hand */
  .sparky-pan-hand {
    animation: sparky-pan-hand 2s linear infinite alternate-reverse both;
  }

  @keyframes sparky-pan-hand {
    0%,
    100% {
      -webkit-transform: rotate(0deg);
      transform: rotate(0deg);
    }
    50% {
      transform: rotate(10deg);
    }
  }

  /* sparky wobbling animation */
  .sparky-wobble {
    animation: sparky-wobble 2s linear infinite alternate-reverse both;
  }

  @keyframes sparky-wobble {
    0%,
    100% {
      transform: translateX(0%);
      transform-origin: 50% 50%;
    }
    50% {
      transform: translateX(15px) rotate(7deg);
    }
  }

  /* stormy wobbling animation */
  .stormy-wobble {
    animation: stormy-wobble 2s linear infinite alternate-reverse both;
  }

  @keyframes stormy-wobble {
    0%,
    100% {
      transform: translateX(0%);
      transform-origin: 50% 50%;
    }
    50% {
      transform: translateX(-15px) rotate(-7deg);
    }
  }

  /* stormy's hand waving animation */
  .stormy-hand {
    animation: stormy-hand 1s linear infinite alternate-reverse both;
  }

  @keyframes stormy-hand {
    0% {
      -webkit-transform: rotate(0);
      transform: rotate(0);
    }
    100% {
      -webkit-transform: rotate(7deg);
      transform: rotate(7deg);
    }
  }

  /* sparky's hand waving animation */
  .sparky-hand {
    animation: sparky-hand 1s linear infinite alternate-reverse both;
  }

  @keyframes sparky-hand {
    0% {
      -webkit-transform: rotate(0);
      transform: rotate(0);
    }
    100% {
      -webkit-transform: rotate(-7deg);
      transform: rotate(-7deg);
    }
  }

  .title {
    display: flex;
    flex-direction: column;
    align-items: end;
  }

  .title1,
  .title2,
  .year {
    font-family: "Coiny";
    color: #57392e;
    line-height: 100%;
  }

  .title1 {
    font-size: 90px;
  }

  .title2 {
    font-size: 125px;
  }

  .year {
    font-size: 50px;
  }

  @media (max-width: 1200px) {
    .title1 {
      font-size: 70px;
    }

    .title2 {
      font-size: 100px;
    }

    .year {
      font-size: 40px;
    }
  }

  @media (max-width: 640px) {
    /* for small screen size */

    .title1 {
      font-size: 40px;
    }

    .title2 {
      font-size: 60px;
    }

    .year {
      font-size: 20px;
    }
  }
</style>
