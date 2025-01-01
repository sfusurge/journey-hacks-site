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
      background-image: url("bg.svg");
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

    .navbar-space {
      padding-top: 80px;
      background-color: rgb(188,201,132);
    }
  
    @media (max-width: 900px) {
    .background {
      align-items: center;
    }

    .title {
      position: static;
      transform: none;
      text-align: center;
      margin: 0;
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      line-height: 0.9;
    }

    .big-text {
      font-size: 60px;
    }
    
    .year {
      position: static;
      align-self: flex-end;
      margin-top: 10px;
      margin-right: 50px;
    }
  }

  </style>
  <div class="navbar-space"></div>
  <div class="background">
    <div class="overlay"></div>
  
    <div class="title">
      <p class="big-text">JOURNEY HACKS</p>
      <p class="year">2025</p>
    </div>
  </div>
  