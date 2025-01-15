<div class="">
    <div class="relative bg-[#8F6455]">
        <img src="/home-animated/background.png" alt="background" class="w-full h-auto">
        <img src="/home-animated/foreground.png" alt="foreground" class="w-full h-auto absolute bottom-0 z-50">
        
        <div class="origin-[30.09259%_100%] stormy-wobble absolute left-[27.39583%] top-[33.1625%] z-20 w-[23.8640625%] h-auto">
          <img src="/home-animated/stormy_head_body.png" alt="stormy" class="absolute w-[75.2962744713%] h-auto z-20">
          <img src="/home-animated/stormy_hand_wave.png" alt="stormy's hand" class="stormy-hand absolute w-[50.020733%] mt-[18.18%] h-auto left-[49.9792662433%] z-10 origin-[27.488110%_66.881468%]">
         </div>
        
        <img src="/home-animated/sparky_hand_wave.png" alt="sparky's hand" class="absolute w-[11.937%] h-auto top-[39.9707%] left-[48.802083%] z-30">
        <img src="/home-animated/sparky_head_body.png" alt="sparky" class="absolute w-[15.090625%] h-auto top-[22.34407%] left-[54.479167%] z-40">

        <img src="/home-animated/sparky_arm_with_pan.png" alt="sparky's frying pan" class="absolute w-[22.861979%] h-auto top-[47.29136%] left-[46.71875%] z-50">
        <img src="/home-animated/fish.png" alt="fish" class="absolute w-[8.3854167%] h-auto top-[57.61347%] left-[47.7083%] z-[60]">
    </div>
</div>

<style>
    /* stormy wobbling animation */
.stormy-wobble {
	-webkit-animation: stormy-wobble 3s linear infinite alternate-reverse both;
	        animation: stormy-wobble 3s linear infinite alternate-reverse both;
}


@keyframes stormy-wobble{
    0%,
  100% {
    -webkit-transform: translateX(0%);
            transform: translateX(0%);
    -webkit-transform-origin: 50% 50%;
            transform-origin: 50% 50%;
  }
  50% {
    -webkit-transform: translateX(-15px) rotate(-3.6deg);
            transform: translateX(-15px) rotate(-3.6deg);
  }
}
    
/* sparky's hand waving animation */
    .stormy-hand {
        animation: rotate-15-cw 1.5s linear infinite alternate-reverse both;
    }
    
    @keyframes rotate-7-cw {
        0% {
            -webkit-transform: rotate(0);
            transform: rotate(0);
        }
        100% {
            -webkit-transform: rotate(7deg);
            transform: rotate(7deg);
        }
    }

    @keyframes rotate-15-cw {
        0% {
            -webkit-transform: rotate(0);
            transform: rotate(0);
        }
        100% {
            -webkit-transform: rotate(10deg);
            transform: rotate(10deg);
        }
    }
</style>