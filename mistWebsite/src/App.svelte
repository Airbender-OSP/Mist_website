<script>
  import Docs from './components/Docs.svelte';
  import Home from './components/Home.svelte';
  import Features from './components/Features.svelte';
  import About from './components/About.svelte';
  // import githubIcon from '../public/assets/github120.png';

  import Tutorial from './components/Tutorial.svelte';
  import Team from './components/Team.svelte';

  let homeToggle = true;
  let docsToggle = false;
  let tutorialToggle = false;

  const docs = () => {
    homeToggle = false;
    docsToggle = true;
    tutorialToggle = false;
  };

  const tutorial = () => {
    homeToggle = false;
    docsToggle = false;
    tutorialToggle = true;
  };

  const home = () => {
    homeToggle = true;
    docsToggle = false;
    tutorialToggle = false;
  };
</script>

<header>
  <h1 class="mist">mist</h1>
  <div class="header-div">
    {#if homeToggle}
      <button on:click={() => docs()}>Docs</button>
      <button on:click={() => tutorial()}>Tutorial</button>
    {/if}
    {#if docsToggle}
      <button on:click={() => home()}>Home</button>
      <button on:click={() => tutorial()}>Tutorial</button>
    {/if}
    {#if tutorialToggle}
      <button on:click={() => home()}>Home</button>
      <button on:click={() => docs()}>Docs</button>
    {/if}
    <a href="google.com"
      ><img src="../public/assets/github120.png" alt="Github Link" /></a
    >
    <!-- <a href="#"><img /></a> -->
  </div>
</header>

<main>
  {#if homeToggle}
    <Home />
  {/if}
  {#if docsToggle}
    <Docs />
  {/if}
  {#if tutorialToggle}
    <Tutorial />
  {/if}
</main>

<footer>
  <!-- <button on:click={() => home()}>Back to home page</button> -->
</footer>

<style>
  header {
    border-bottom: solid;
    border-width: 3px;
    display: flex;
    justify-content: space-between;
  }
  /* .mist {
  } */
  .header-div {
    width: 10%;
    margin-right: 2em;
    margin-left: 2em;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
  button {
    height: 2em;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
