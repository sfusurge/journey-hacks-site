<style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
  
    .background {
      background-color: #8F6455;
      width: 100vw;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-end;
      padding: 20px;
      overflow: hidden;
      position: relative;
    }
  
    .overlay {
      background-image: url("../assets/bg.png");
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      z-index: 1;
    }
  
    .title {
      max-width: 300px;
      text-align: right;
      margin-top: 40px;
      margin-right: 50px;
      position: relative;
      z-index: 2;
    }
  
    .year {
      text-align: right;
    }
  
    .big-text {
      font-size: 70px;
      color: #664848;
    }
  
    @media (max-width: 800px) {
      .title {
        position: absolute;
        top: 20px;
        left: 50%;
        transform: translateX(-50%);
        text-align: center;
        margin-top: 0;
        margin-right: 0;
        margin-left: 0;
        width: auto;
      }
  
      .big-text {
        font-size: 40px;
      }
    }
  </style>
  
  <div class="background">
    <div class="overlay"></div>
  
    <div class="title">
      <p class="big-text">Journey Hacks</p>
      <p class="year">2025</p>
    </div>
  </div>
  