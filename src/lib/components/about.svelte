<style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
  
    .background {
      background-image: url("../assets/bg-about.png");
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      width: 100vw;
      height: 100vh;
      position: relative;
    }
  
    .content-container {
      position: absolute;
      top: 60%;
      right: 50px;
      transform: translateY(-50%);
      width: 350px;
      background-color: #8F6455;
      color: #FFEBDD;
      border-radius: 15px;
      padding: 20px;
      box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
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
      width: 80%;
      height: 100%;
      object-fit: cover;
    }
  
    .header-text {
      position: absolute;
      top: 50%;
      left: 40%;
      transform: translate(-50%, -50%) rotate(-10deg);
      color: #835242;
      font-size: 30px;
      font-weight: bold;
      z-index: 2;
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
  
    .mobile-image {
      display: none;
    }
  
    @media screen and (max-width: 600px) {
      .background {
        background-image: none;
        height: auto;
      }
  
      .content-container {
        position: static;
        width: 100%;
        transform: none;
        border-radius: 0;
        padding: 20px;
      }
  
      .header-container {
        border-radius: 0;
      }
  
      .mobile-image {
        display: block;
        width: 100%;
        height: 100%;
      }
  
      .header-image {
        width: 60%;
        height: 100%;
        object-fit: cover;
      }
  
      .header-text {
        position: absolute;
        top: 50%;
        left: 30%;
        transform: translate(-50%, -50%) rotate(-10deg);
        color: #835242;
        font-size: 30px;
        font-weight: bold;
        z-index: 2;
      }
  
      .mobile-special {
        margin-left: 20px;
      }
    }
  </style>
  
  <div class="background">
    <div class="content-container">
      <div class="header-container">
        <img src="header.png" alt="Header" class="header-image">
        <div class="header-text">About</div>
      </div>
  
      <div class="section mobile-special">
        <div class="section-text">
          JourneyHacks is an introductory Hackathon experience where you will be able to Connect, Create, and Conquer!
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
          Immerse yourself in hands-on workshops led by industry experts covering a variety of essential tech-related topics.
        </div>
      </div>
  
      <div class="section special">
        <div class="section-title">Conquer</div>
        <div class="section-text">
          When the sun sets, present your innovation to our panel of judges for a chance to win prizes and gain recognition for your hard work.
        </div>
      </div>
    </div>
    <img src="bg-about.png" alt="About Background" class="mobile-image">
  </div>
  