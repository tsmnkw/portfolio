<script>
import { fly } from 'svelte/transition';
import { onMount } from "svelte";
import { dark_mode } from "./store"

window.scrollTo(0, 0);

// transition elements in as they enter view
onMount(() => {
    const observer = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
            if (entry.isIntersecting) {
                entry.target.classList.add('show');
            }
        });
    });

    const hidden_elements = document.querySelectorAll('.hidden');

    hidden_elements.forEach((el) => observer.observe(el));
    
});
</script>

<div class="grid" in:fly={{x: -400, duration: 500}}>
    <a href="https://tsmnkw.github.io/giddy-grocery/" target="_blank">
        <img src="/images/giddy-grocery.jpg">
    </a>

    <div class="grid-content">
        <div class="card" style="background-color: {$dark_mode ? 'rgba(25, 26, 33, 0.9)' : 'rgba(238, 238, 238, 0.9)'};">
            <h2>Giddy Grocery - online store</h2>

            <div class="link-div">
                <img class="icon" src={$dark_mode ? "./images/link-light.png" : "./images/link.png"} alt="">
                <a href="https://tsmnkw.github.io/giddy-grocery/">Web link</a>
                <img class="icon" src={$dark_mode ? "./images/github-light.png" : "./images/github.png"} alt="">
                <a href="https://github.com/tsmnkw/giddy-grocery">Github repo</a>
            </div>

            <h3>Description</h3>
            <p>This website was a project initally built for a university assignment. The project
                had a specification to fulfill including: the use of image maps for the catalogue, 
                a product details section, a functional shopping cart, and a checkout confirmation and order form page.  
            </p>
            <p>For the assignment the app was built with php on a linux server, and a mysql database for the backend on AWS.
                However, i have since re-written the php code in javascript on the front end, accompanied with json instead of
                mysql - in order to more easily host the website on github.
                I managed to get perfect marks for this uni project.
            </p>

            <h3>Technology stack</h3>
            <p>This website is built with <span style="color: #eddc67">javascript</span>, jquery, php, sql, json, css, html, and initially with AWS elastic beanstalk.</p>
        </div>
    </div>

    <a href="https://tsmnkw.github.io/" target="_blank">
        <img class="hidden" src="/images/portfolio.jpg">
    </a>

    <div class="grid-content hidden">
        <div class="card" style="background-color: {$dark_mode ? 'rgba(25, 26, 33, 0.9)' : 'rgba(238, 238, 238, 0.9)'};">
            <h2>This portfolio website</h2>

            <div class="link-div">
                <img class="icon" src={$dark_mode ? "./images/link-light.png" : "./images/link.png"} alt="">
                <a href="https://tsmnkw.github.io/">Web link</a>
                <img class="icon" src={$dark_mode ? "./images/github-light.png" : "./images/github.png"} alt="">
                <a href="https://github.com/tsmnkw/tsmnkw.github.io">Github repo</a>
            </div>

            <h3>Description</h3>
            <p>The website you are currently looking at!</p>
            <p>It hosts my coding and design projects.
                It is a SPA style svelte website. It features a custom sweeping navagation system, responsive grid
                layouts, interactive mobile-style web apps, and a dark/light mode toggle.
            </p>

            <h3>Technology stack</h3>
            <p>This website is built with <span style="color: #eb5027">svelte</span>, javascript, css, and html. This website utilises a 
                single page app (SPA) design - for the time being.</p>
        </div>
    </div>

    <a href="https://artistwebsite.vercel.app/" target="_blank">
        <img class="hidden" src="/images/artist-website.jpg">
    </a>

    <div class="grid-content hidden">
        <div class="card" style="background-color: {$dark_mode ? 'rgba(25, 26, 33, 0.9)' : 'rgba(238, 238, 238, 0.9)'};">
            <h2>Artist website</h2>

            <div class="link-div">
                <img class="icon" src={$dark_mode ? "./images/link-light.png" : "./images/link.png"} alt="">
                <a href="https://artistwebsite.vercel.app/">Web link</a>
                <img class="icon" src={$dark_mode ? "./images/github-light.png" : "./images/github.png"} alt="">
                <a href="https://github.com/tsmnkw/artist-website">Github repo</a>
            </div>

            <h3>Description</h3>

            <p>This is an example website depicting a fictional artist's website. I developed this site to learn and practice the Nuxt Vue.js framework, including its markdown headless CMS (content management system) capabilities.</p>
            <p>In order to provide gallery content to this artist website, i used some very basic (and admittedly bad) generative art that i created one afternoon while i was having fun experimenting with Matt DesLauriers' awesome canvas-sketch framework.</p>

            <h3>Technology stack</h3>
            <p>This website is built with the <span style="color: #64b586">nuxt framework</span> (a vue.js framework), the nuxt content plugin, javascript, css, and html.</p>
        </div>
    </div>

    <a href="https://tsmnkw.github.io/psuedo-business/" target="_blank">
        <img class="hidden" src="/images/car-rental.jpg">
    </a>

    <div class="grid-content hidden">
        <div class="card" style="background-color: {$dark_mode ? 'rgba(25, 26, 33, 0.9)' : 'rgba(238, 238, 238, 0.9)'};">
            <h2>Car rental - fake business</h2>

            <div class="link-div">
                <img class="icon" src={$dark_mode ? "./images/link-light.png" : "./images/link.png"} alt="">
                <a href="https://tsmnkw.github.io/psuedo-business/">Web link</a>
                <img class="icon" src={$dark_mode ? "./images/github-light.png" : "./images/github.png"} alt="">
                <a href="https://github.com/tsmnkw/psuedo-business">Github repo</a>
            </div>

            <h3>Description</h3>
            <p>This website was also a project built for a university assignment. The project had a specification to follow which included:
                accessing and displaying a self-generated json data set of cars for rent, a functional shopping cart, and a checkout form (among many other details).</p>
            <p>The project was mainly to get us as students working with javascript, jquery, and introducing us to working with json data (after previously learning xml).
                Fortunately i managed to get perfect marks for this project also.
            </p>

            <h3>Technology stack</h3>
            <p>This website is built with <span style="color: #eddc67">vanilla javascript</span>, jquery, json, css, and html.</p>
        </div>
    </div>
</div>

<style>
.grid {
    display: grid;
    grid-auto-flow: row;
    grid-template-columns: 1fr;
    column-gap: 50px;
    row-gap: 20px;
    place-items: center;
    justify-items: center;
}

.card {
    padding: 5px 20px 5px 20px;
    border-radius: 10px;
}

h3 {
    color: #7e9ec7;
}

img {
    max-width: 100%;
    border-radius: 10px;
}

.icon {
    width: 20px;
}

.link-div {
    display: grid;
    place-items: left;
    grid-template-rows: 1fr;
    grid-template-columns: 20px 100px 20px 1fr;
    gap: 5px;
    line-height: 20px;
}


@media (min-width: 750px) {
    .grid {
        row-gap: 50px;
    }
}

@media (min-width: 1100px) {
    .grid {
        grid-template-columns: 5fr 3fr;
        row-gap: 180px;
    }
}

</style>