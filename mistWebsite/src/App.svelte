<script>
  import Docs from './components/Docs.svelte';
  import Home from './components/Home.svelte';

  import About from './components/About.svelte';

  import Tutorial from './components/Tutorial.svelte';
  import Team from './components/Team.svelte';

  let mistLogo = '/images/mistLogo.png';
  let githubIcon = '/assets/github120.png';
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
  <!-- <h1 class="mist">mist</h1> -->
  <img src={mistLogo} alt="logo" id="mistLogoHeader" />
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
    <a href="https://github.com/oslabs-beta/mist/tree/dev"
      ><img
        src={githubIcon}
        alt="Github Link"
        id="githubHeader"
        style="margin:5px"
      /></a
    >
    <!-- <a href="#"><img /></a> -->
  </div>
</header>

<main>
  {#if homeToggle}
    <Home on:click={() => tutorial()} />
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

<style global lang="scss">
  header {
    border-bottom: solid;
    border-color: #9d9d9d;
    border-width: 3px;
    display: flex;
    justify-content: space-between;
    padding-left: 60px;
    height: 6em;
  }
  #mistLogoHeader {
    height: 5em;
  }
  #githubHeader {
    width: 50px;
    height: 50px;
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
    color: #6194bc;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
  h2 {
    color: #6194bc;
    text-transform: uppercase;
    font-size: 2em;
    font-weight: 100;
  }
  p {
    font-size: 1.3em;
    font-weight: 200;
  }
  button {
    height: 3em;
    font-weight: 100;
    border: 1px solid #9d9d9d;
    border-radius: 4px;
    margin: 4px;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
