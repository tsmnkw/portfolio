<script>
import { nav, title, dark_mode } from './store.js';
import { fly } from 'svelte/transition';
import card_1 from '../assets/apps.jpg';
import card_2 from '../assets/giddy-grocery.jpg';
import card_3 from '../assets/persona-collage.jpg';
import card_4 from '../assets/waves.jpeg';
import dark from  '../assets/background-dark.png';
import light from  '../assets/background-light.png';

window.scrollTo(0, 0);


function toggle(num) {
  for (let i = 1; i < $nav.length - 1; i++) {
    $nav[i].visible = false;
  }
  $nav[num].visible = true;
  $title = $nav[num].name;
}
</script>

<div class="outer-grid" in:fly={{x: -400, duration: 500}}>
    <div class="intro" style="background-color: {$dark_mode ? 'rgba(25, 26, 33, 0.9)' : 'rgba(238, 238, 238, 0.9)'};">
        <p>Hello, Tasman here. This is my portfolio page. <br>
            Please feel free to browse my projects if you like 😊
        </p>
    </div>


    <div class="inner-grid">
        <div class="img" style="background-image: url({card_1})" on:click={() => toggle(2)}>
            <div class="card-txt"><span>Web apps</span></div>
        </div>
        <div class="img" style="background-image: url({card_2})" on:click={() => toggle(3)}>
            <div class="card-txt"><span>Websites</span></div>
        </div>
        <div class="img" style="background-image: url({card_3})" on:click={() => toggle(4)}>
            <div class="card-txt"><span>Design porfolio</span></div>
        </div>
        <div class="img" style="background-image: url({card_4})" on:click={() => toggle(5)}>
            <div class="card-txt"><span>About</span></div>
        </div>
    </div>

</div>

<style>
.outer-grid {
    display: grid;
    grid-auto-flow: row;
    grid-template-rows: 100px 8fr;
    height: calc(100vh - 90px);
    width: 100%;
    text-align: center;
    row-gap: 15px;
}

.intro {
    display: grid;
    place-content: center;
    border-radius: 15px;
    width: max-content;
    place-self: center;
    padding-left: 20px;
    padding-right: 20px;
}

p {
    font-size: 14px;
    line-height: 20px;
}

.inner-grid {
    display: grid;
    grid-auto-flow: row;
    grid-template-rows: 1fr 1fr 1fr 1fr;
    grid-template-columns: 1fr;
    gap: 20px;
    place-items: center;
    height: calc(100vh - 205px);
}

.img {
    background-size: cover;
    background-repeat: no-repeat;
    background-color: #191a21;
    width: 100%;
    height: 100%;
    border-radius: 15px;
    cursor: pointer;
    transition: all 0.5s;
}

.img:hover {
    opacity: 1;
}

.card-txt:hover {
    opacity: 1;
}

.card-txt {
    font-size: 2rem;
    font-weight: 200;
    opacity: 1;
    height: 100%;
    width: 100%;
    display: flex;
    place-items: center;
    justify-content: center;
    transition: all 0.5s;
}

span {
    background-color: #000;
    color: #fff;
    border-radius: 5px;
    opacity: 0.9;
    padding-left: 5px;
    padding-right: 5px;
}

@media (min-width: 750px) {
    .inner-grid {
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr 1fr;
        height: calc(100vh - 225px);
    }
    .img {
        height: calc((100vh - 225px)/2);
    }

    .img:hover {
        padding: 0px 5px;
        border-radius: 20px;
    }

    .card-txt {
        font-size: 2.3rem;
    }

    p {
        font-size: 20px;
        line-height: 24px;
    }
}

@media (max-width: 380px) {
    .card-txt {
        font-size: 1.8rem;
    }
}

</style>
