<script>
    import { fly } from 'svelte/transition';
    import { dark_mode } from './store.js';

    window.scrollTo(0, 0);
</script>

<div class="content-div" in:fly={{x: -400, duration: 500}}>
    <img src="./images/choco-profile.jpg" alt="">

    <div class="card" style="background-color: {$dark_mode ? 'rgba(25, 26, 33, 0.9)' : 'rgba(238, 238, 238, 0.9)'};">
        <span style="padding-top: 30px;">About me</span>
        <p>Hello! My name is Tasman. <br><br>
            Thank you for finding your way to my portfolio page. Be sure to hang around and take a look at my projects if you'd like.<br>
            I appreciate your time and curiosity.<br><br>
            You can contact me at <a href="mailto: " style="color: #78b2aa;"></a></p><br>

        <span style="padding-top: 30px;">About this website</span>
        <p>This website is my portfolio of web apps, websites, and design projects.<br><br>
            Some notes on the features - for easier navigation:</p>
            <ul><span>⦿</span> The web apps are all displayed within iframes, so you can interact with them without leaving the page.</ul>
            <ul><span>⦿</span> All of the web apps and websites will work on both desktop and mobile devices, so please feel free
            to open anything in a new tab to view them in fullscreen, or view them on your device.</ul> 
            <ul><span>⦿</span> With some of the projects you will notice that the design is slightly different depending on the device, featuring a responsive css design.</ul>
            <ul><span>⦿</span> The design page allows you to click on the images to view them fullpage.</ul>
            <ul><span>⦿</span> There is a light/dark mode for your preference of theme, the toggle is located in the top right corner as the ☯︎ symbol.</ul>

    </div>
</div>

<style>
    .content-div {
        display: grid;
        grid-auto-flow: row;
        row-gap: 35px;
    }

    .card {
        padding: 10px 20px 10px 20px;
        border-radius: 10px;
    }

    img {
        max-width: 200px;
        border-radius: 50%;
        margin: 20px auto auto auto;
    }

    span {
        color: #7e9ec7;
        font-size: 1.5rem;
    }

    @media (min-width: 800px) {
        .content-div {
            margin-left: 20%;
            margin-right: 20%;
        }
    }
</style>
