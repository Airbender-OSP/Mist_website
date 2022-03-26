<script>
  import About from './About.svelte';

  import Team from './Team.svelte';
  import { fade, fly, scale, blur, slide } from 'svelte/transition';
  import { circIn } from 'svelte/easing';
  let dog = '/images/dog.png';
  let corgi = '/images/corgi.jpeg';
  let pupps = 'images/puppies.jpeg';
  let cutie = 'images/cutie.jpeg';

  let y;
  $: console.log(y);
  let modalOpen = true;
  $: console.log(window.screen.availHeight);
  console.log('../../public/images/dog.png');
</script>

<svelte:window bind:scrollY={y} />

<div class="About">
  <About on:click />
</div>
<div>
  <Team />
</div>

<!-- {/if} -->
<style>
  .features {
    margin-top: 85px;
    border: solid;
    width: 90%;
    padding-bottom: 20px;
    /* font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
      Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif !important; */
  }
  .features img {
    float: center;
    width: 100px;
    height: 100px;
    object-fit: cover;
  }
  p {
    color: black;
    text-align: left;
    padding-left: 10px;
    max-width: 40%;
    float: left;
  }
  div {
    margin: auto;
    width: 95%;
    border-width: 1px;
    border-radius: 20px;
    border-color: #9d9d9d !important;
    /* border: solid; */
    margin-top: 20px;
    margin-bottom: 20px;
  }
  h1 {
    color: #6194bc;
  }
  h2 {
    text-align: left;
    padding-left: 10px;
    color: #6194bc;
    font-size: 2em;
    /* font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
      Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif !important; */
  }
</style>
