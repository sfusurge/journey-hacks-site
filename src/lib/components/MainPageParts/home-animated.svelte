<div class="">
 
  
  <div class="bg-[#c4d086] relative h-40 xl:h-12">
  </div>
  
  <div class="relative bg-[#8F6455]">
    <div class="title absolute right-8 -top-20 xl:top-8">
      <span class="font-coiny text-xl md:text-3xl">FEB 14, 2025</span>
      <h1 class="title1 font-coiny text-5xl">JOURNEY</h1>
      <h1 class="-mt-2 md:-mt-4 title2">HACKS</h1>
    </div>
    
    <img
      src="/home-animated/background.png"
      alt="background"
      class="w-full h-auto"
    />
    <img
      src="/home-animated/foreground.png"
      alt="foreground"
      class="w-full h-auto absolute bottom-0 z-[50]"
    />

    <div
      class="stormy-wobble absolute left-[27.39583%] top-[33.1625%] z-20 w-[23.8640625%] h-[37.4450951684%]"
    >
      <img
        src="/home-animated/stormy_head_body.png"
        alt="stormy"
        class="absolute w-[75.2962744713%] h-auto z-20"
      />
      <img
        src="/home-animated/stormy_hand_wave.png"
        alt="stormy's hand"
        class="stormy-hand absolute w-[50.020733%] top-[18.18%] h-auto left-[49.9792662433%] z-10 origin-bottom-left"
      />
    </div>

  

    <div
      class="sparky-wobble w-[22.8619791667%] h-[47.9707174231%] absolute left-[48.80208%] top-[22.34407%]"
    >
      <img
        src="/home-animated/sparky_hand_wave.png"
        alt="sparky's hand"
        class="sparky-hand absolute w-[57.478557456%] h-auto top-[36.7445977292%] z-30 origin-bottom-right"
      />
      <img
        src="/home-animated/sparky_head_body.png"
        alt="sparky"
        class="absolute w-[72.6638912575%] h-auto right-0 z-40"
      />

    
    </div>

    <div
        class="sparky-wobble w-[22.8619791667%] h-[47.9707174231%] absolute left-[46.71875%] top-[22.34407%] z-[60]"
      >
        <img
          src="/home-animated/sparky_arm_with_pan.png"
          alt="sparky's frying pan"
          class="sparky-pan-hand absolute w-full h-auto left-[8%] top-[56.00524%] origin-[87.025%_20.8%]"
        />

        <img
          src="/home-animated/fish.png"
          alt="fish"
          class="fish absolute w-[36.6784371796%] z-[40] left-[9.32%] top-[70.5227%] h-auto origin-center"
        />
      </div>
  </div>
</div>

<style>
/* fish */
.fish {
       animation: bounce 1s ease-in;
			animation-iteration-count:infinite;
			 animation-direction: alternate;
}

@keyframes bounce{
 from {
	 transform: translateY(-200%);
 }

	to {
		transform:  translateY(0%);
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
        transform: rotate(-20deg) translateY(-300%)
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
    0%, 100% {
      -webkit-transform: rotate(0deg);
      transform: rotate(0deg);
    }
    50% {
      transform: rotate(7.5deg);
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
    width: fit-content;
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

  @media (max-width: 768px) {
    /* for small screen size */

    .title1 {
      font-size: 40px;
    }

    .title2 {
      font-size: 60px;
    }

    .year {
      font-size: 12px;
    }
  }
</style>
