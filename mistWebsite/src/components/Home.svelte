<script>
  import About from './About.svelte';
  import Features from './Features.svelte';
  import Team from './Team.svelte';
  import { fade, fly, scale, blur, slide } from 'svelte/transition';
  import { circIn } from 'svelte/easing';
  let dog = '/images/dog.png';
  let corgi = '/images/corgi.jpeg';
  let pupps = 'images/puppies.jpeg';
  let cutie = 'images/cutie.jpeg';

  let y;
  $:console.log(y);
  let modalOpen = true;
  $:console.log(window.screen.availHeight);
  console.log('../../public/images/dog.png');
</script>


<svelte:window bind:scrollY={y} />

<div class="About">
  <About />
</div>

{#if y > 105 || window.screen.availHeight > 1000}
  <!-- <div transition:fade={{ opacity: 0.1 }}>
  <Features /> -->
  <div class="features" transition:fade={{ opacity: 0.1 }}>
    <h1>Features</h1>

    {#if y > 105}
      <div class='startbutton' transition:slide={{ x: 400, delay: 50, duration: 400, easing: circIn }}>
        <h2>Start Button</h2>
        <p>
        Start button 'on click' sends a fetch request to the user's linked SQL
        database. The fetch request sends a custom query to get the users current
        session number.
      </p>
      <img src={dog} alt="dog" height='500px' width='1000px' float='right'/>
      </div>
    {/if}
    
    {#if y > 690}
      <div class='stopbutton' transition:slide={{ x: 400, delay: 100, duration: 400, easing: circIn }}>
        <h2>Stop Button</h2>
        <p>
        Stop Button 'on click' sends a SQL query that gathers all metric data from
        the users metric table in their SQL database where the session number is
        equal to the current session number.
        </p>
        <img src={corgi} alt='corgi' height='500px' width='1000px'/>
      </div>
    {/if}
    
    {#if y > 1300}
      <div class='generatemetrics' transition:slide={{ x: 400, delay: 100, duration: 1000, easing: circIn }}>
        <h2>Generate Metrics</h2>
        <p>Track your metrics with the click of a button! Track your metrics with the click of a button! Track your metrics with the click of a button!</p>
        <img src={pupps} alt='pups' height='500px' width='1000px'/>
      </div>
    {/if}

    {#if y > 1900}
      <div class='stopbutton' transition:slide={{ x: 400, delay: 100, duration: 1000, easing: circIn }}>
        <h2>Clear Metrics</h2>
        <img src={cutie} alt='cutie' height='500px' width='1000px'/>
      </div>
    {/if}

  </div>
  <!-- </div> -->
{/if}

{#if y > 405}
<div>
  <Team />
</div>
{/if}

<style>
  .features{
    margin-top: 85px;
    border: solid;
    width: 90%;
    padding-bottom: 20px;
  }
   p {
    color: black;
    text-align: left;
    padding-left: 10px;
    max-width: 40%;
    float:left;
  }
  div {
    margin: auto;
    width: 95%;
    border-width: 1px;
    border-radius: 20px;
    border-color: grey;
    /* border: solid; */
    margin-top: 20px;
    margin-bottom: 20px;
  }
  h1 {
    color: blue;
  }
  h2 {
    text-align: left;
    padding-left: 10px;
    color: #EB984E;
    font-size: 2em;
  }
</style>
