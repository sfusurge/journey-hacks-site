<script lang="ts">
    import StickyLabel from "../StickyLabel.svelte";

</script>
<div class="background">
  <div class="content-container">
    <StickyLabel>About</StickyLabel>

    <div class="section mobile-special">
      <div class="section-text">
        JourneyHacks is an introductory Hackathon experience where you will be
        able to Connect, Create, and Conquer!
      </div>
    </div>

    <div class="section special">
      <div class="section-title">Connect</div>
      <div class="section-text">
        Start the day by forming alliances during our team formation event!
      </div>
    </div>

    <div class="section special">
      <div class="section-title">Create</div>
      <div class="section-text">
        Immerse yourself in hands-on workshops led by industry experts covering
        a variety of essential tech-related topics.
      </div>
    </div>

    <div class="section special">
      <div class="section-title">Conquer</div>
      <div class="section-text">
        When the sun sets, present your innovation to our panel of judges for a
        chance to win prizes and gain recognition for your hard work.
      </div>
    </div>
  </div>
  <img src="/bg-about.svg" alt="About Background" />
</div>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .background {
    width: 100%;
    /* height: 100vh; */
    position: relative;
  }

  .content-container {
    position: absolute;
    top: 60%;
    right: 50px;
    transform: translateY(-50%);
    width: 350px;
    background-color: rgba(87, 57, 46, 1);
    color: #ffebdd;
    border-radius: 15px;
    padding: 25px;
    font-family: Arial, sans-serif;
    
  }

  .header-container {
    position: relative;
    width: 100%;
    height: 120px;
    border-radius: 15px 15px 0 0;
    overflow: hidden;
    
  }

  .header-image {
    width: 100%;
    height: auto;
    object-fit: cover;
  }

  .header-text {
    position: absolute;
    top: 50%;
    left: 40%;
    transform: translate(-50%, -50%) rotate(-10deg);
    color: #835242;
    font-size: 40px;
    font-weight: bold;
    z-index: 2;
    font-family: "Coiny", sans-serif;
  }

  .section {
    margin-top: 20px;
  }

  .section-title {
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 5px;
  }

  .section-text {
    font-size: 14px;
    line-height: 1.5;
  }

  .special {
    margin-left: 20px;
  }

  img {

    width: 100%;
    max-width: unset;
  }


  @media screen and (max-width: 900px) {


    img {
        width: 100%;
        height: auto;
    }


    .background{
        height: fit-content;
    }

    .content-container {
      position: static;
      width: 100%;
      transform: none;
      border-radius: 0;
      padding: 20px;
      background-color: #8f6455;
      padding-bottom: 75px;
    }

    .header-container {
      border-radius: 0;
    }


    .header-text {
      position: absolute;
      top: 50%;
      left: 150px;
      color: #835242;
      font-size: 40px;
      font-weight: bold;
      z-index: 2;
    }

    .mobile-special {
      margin-left: 20px;
      margin-top: 75px;
    }
  }
</style>
