<div class="background" id="apply">
    <img src="butter.svg" class="corner butter" alt="Butter" />
    <img src="pin.svg" class="corner pin" alt="Pin" />
    <img src="bowl.svg" class="corner bowl" alt="Bowl" />
    <img src="sugar.svg" class="corner sugar" alt="Sugar" />
    <div class="center">
        <img src="center.svg" class="center-image" alt="Center" />
        <div class="buttons">
            <button class="btn">Hacker</button>
            <button class="btn">Mentor</button>
        </div>
    </div>

    <div class="title"></div>
</div>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .background {
        background-image: url("/bg-apply.svg");
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
        height: auto;
        z-index: 2;
    }

    .butter {
        top: 150px;
        left: -120px;
        width: 450px;

    }

    .sugar {
        top: 20px;
        right: 20px;
    }

    .pin {
        bottom: 190px;
        left: -100px;
        width: 520px;
    }

    .bowl {
        bottom: 60px;
        right: -150px;
        width: 450px;
    }

    .center {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 3;
        text-align: center;
        width: 90dvw;
        min-width: 400px;
        max-width: 900px;
    }

    .center-image {
        display: block;
        width: 100%;
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
        background-color: #57392e;
        border-radius: 5px;
        border: none;
        cursor: pointer;
        transform-origin: center;
        transition:
            scale 0.3s ease-out,
            filter 0.3s ease-out;
    }

    .btn:nth-child(2) {
        transform: rotate(15deg);
    }

    .btn:nth-child(1) {
        transform: rotate(-15deg);
    }

    .btn:hover {
        scale: 1.1;
        filter: brightness(1.05);
    }
    .btn:active{
        scale: 0.96;
        filter: brightness(0.74);
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
            top: calc(50% - 450px);
            left: calc(50% - 650px);
            width: 450px;
        }

        .sugar {
            top: 60px;
            left: calc(50% + 350px );
            width: 350px;
            display: block;
        }

        .pin {
            bottom: 70px;
            left: calc(50% - 450px);
            width: 500px;
        }

        .bowl {
            bottom: 100px;
            left: calc(50% + 250px);
            width: 420px;
        }
    }
</style>
