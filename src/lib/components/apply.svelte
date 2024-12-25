<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.background {
  background-image: url("../assets/bg-apply.png");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  width: 100%;
  height: 100vh;
  position: relative;
  overflow: hidden; 
}

.corner {
  position: absolute;
  width: 250px;
  height: auto;
  z-index: 2;
}

.butter {
  top: 20px;
  left: -100px;
}

.sugar {
  top: 20px;
  right: 20px;
}

.pin {
  bottom: 20px;
  left: -50px;
}

.bowl {
  bottom: 20px;
  right: -80px; 
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 3;
  text-align: center;
  width: 100%;
}

.center-image {
  display: block;
  width: auto;
  height: auto;
  position: relative;
}

.buttons {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 4;
  display: flex;
  gap: 20px;
  margin-top: 30px;
}

.btn {
  padding: 10px 20px;
  font-size: large;
  font-weight: bold;
  color: white;
  border-radius: 5px;
  border: none;
  cursor: pointer;
  transform-origin: center;
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.btn:nth-child(2) {
  background-color: #FFBE77;
  transform: rotate(15deg);
}

.btn:nth-child(1) {
  background-color: #5562EE;
  transform: rotate(-15deg);
}

.btn:hover {
  background-color: #aaa;
}

.sugar {
  display: none;
}

@media (min-width: 800px) {
  .corner {
    width: 300px;
  }

  .buttons {
    gap: 40px;
  }

  .btn {
    padding: 15px 20px;
    font-size: x-large;
  }

  .butter {
    top: 20px;
    left: 20px;
  }

  .sugar {
    top: 20px;
    right: 20px;
    width: 250px;
    display: block;
  }

  .pin {
    bottom: 20px;
    left: 20px;
  }

  .bowl {
    bottom: 20px;
    right: 20px;
  }

  .center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 3;
    text-align: center;
    width: auto;
  }

  .center-image {
    display: block;
    width: auto;
    height: auto;
    position: relative;
  }
}

  </style>
  
  <div class="background">
    <img src="butter.png" class="corner butter" alt="Butter" />
    <img src="pin.png" class="corner pin" alt="Pin" />
    <img src="bowl.png" class="corner bowl" alt="Bowl" />
    <img src="sugar.png" class="corner sugar" alt="Sugar" />
    <div class="center">
      <img src="center.png" class="center-image" alt="Center" />
      <div class="buttons">
        <button class="btn">Hacker</button>
        <button class="btn">Mentor</button>
      </div>
    </div>
  
    <div class="title">
    </div>
  </div>
  