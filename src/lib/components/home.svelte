<style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
  
    .background {
      background-color: #8F6455;
      width: 100%;
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
      position: relative;
      right: 10%;
      z-index: 2;
      font-family: 'Coiny', sans-serif;
      line-height: 1.3;
    }
  
    .year {
      text-align: right;
      color: #664848;
      font-family: 'Coiny', sans-serif;
    }
  
    .big-text {
      font-size: 80px;
      color: #664848;
    }
  
    @media (max-width: 800px) {
      .title {
        position: absolute;
        top: 20px;
        left: 35%;
        transform: translateX(-50%);
        text-align: center;
        margin-top: 20px;
        margin-right: 0;
        margin-left: 0;
        width: auto;
        line-height: 0.8;
      }
  
      .big-text {
        font-size: 60px;
      }
      
      .year {
        position: absolute;
        left: 140%;
      }
    }
  </style>
  
  <div class="background">
    <div class="overlay"></div>
  
    <div class="title">
      <p class="big-text">JOURNEY HACKS</p>
      <p class="year">2025</p>
    </div>
  </div>
  