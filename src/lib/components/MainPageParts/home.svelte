<div class="navbar-space"></div>
<div class="background" id="">
    <div class="overlay"></div>

    <div class="title">
        <h1 class="title1">JOURNEY</h1>
        <h1 class="title2">HACKS</h1>
        <span class="year">2025</span>
    </div>
</div>


<svelte:head>
    <link rel="prefetch" href="/bg.svg" as="image" fetchpriority="high" >
</svelte:head>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .background {
        background-color: #8f6455;
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
        background-image: url("/bg.svg");
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
    }

    .navbar-space {
        padding-top: 80px;
        background-color: rgb(188, 201, 132);
    }

    .title {
        position: absolute;
        right: 5rem;
        top: 2rem;
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

    @media (max-width: 900px) {
/* for small screen size */
        .title {
            right:2rem;
            top: 1rem;
        }

        .title1{
            font-size: 60px;
        }

        .title2{
            font-size: 80px;
        }

        .year{
            font-size: 30px;
        }
    }
</style>
