<script>
  import About from './About.svelte';
  import Features from './Features.svelte';
  import Team from './Team.svelte';
  import { fade, fly, scale, blur, slide } from 'svelte/transition';
  import { circIn } from 'svelte/easing';
  let dog = '../../public/images/dog.png';
  let y;
  $:console.log(y);
  let modalOpen = true;
  $:console.log(window.screen.availHeight);
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
        <img src={dog} alt="dog"/>
        </p>
      </div>
    {/if}
    
    {#if y > 235}
      <div class='stopbutton' transition:slide={{ x: 400, delay: 100, duration: 400, easing: circIn }}>
        <h2>Stop Button</h2>
        <p>
        Stop Button 'on click' sends a SQL query that gathers all metric data from
        the users metric table in their SQL database where the session number is
        equal to the current session number.
        </p>
      </div>
    {/if}
    
    {#if y > 300}
      <div class='generatemetrics' transition:slide={{ x: 400, delay: 100, duration: 1000, easing: circIn }}>
        <h2>Generate Metrics</h2>
        <p>Track your metrics with the click of a button!</p>
      </div>
    {/if}

    {#if y > 400}
      <div class='stopbutton' transition:slide={{ x: 400, delay: 100, duration: 1000, easing: circIn }}>
        <h2>Clear Metrics</h2>
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
