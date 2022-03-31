<script>
  import App from '../App.svelte';
  import Docs from './Docs.svelte';
  import Home from './Home.svelte';
  let npm = '/images/npm.png';
  let cloud = '/images/cloud.png';
  // #f9f9f9
  // #e9e9e9
</script>

<div id="aboutDiv">
  <div id="aboutTitle">
    <h1>About</h1>
  </div>
  <div id="featuresDiv">
    <h3>
      Mist: an application performance monitoring tool for unpublished
      CloudFlare workers.
    </h3>
    <p id="aboutP" style="text-align: left">
      Mist provides a log of the following performance metrics for monitored
      workers:

      <br />
      <br />
      ➡️ &ensp HTTP request and response times<br />
      ➡️ &ensp Request durations<br />
      ➡️ &ensp Response status codes<br />
      ➡️ &ensp History of previously recorded monitoring sessions<br />
    </p>
    <!-- <ul id="bullets" list-style-image="url({cloud})">
      <li>HTTP request and response times</li>
      <li>Request durations</li>
      <li>Response status codes</li>
      <li>History of previously recorded monitoring sessions</li>
    </ul> -->
    <p style="text-align: center">
      Check out the
      <span id="aboutTutLink" style="text-decoration: underline" on:click
        >tutorial</span
      > to get started!
    </p>
  </div>
  <!-- <div id="npmdownloadcontainer"> -->
  <a
    href="https://www.npmjs.com/package/mist-analytics"
    id="npmdownloadcontainer"
  >
    <img alt="npm" src={npm} style="height: 30px" />
    <!-- <span>NPM Download</span> -->
  </a>
  <!-- </div> -->
</div>

<style>
  /* h1 {
    margin-top: 5em;
  } */
  h3 {
    font-weight: 200;
  }
  p {
    font-weight: 100;
  }
  #aboutDiv {
    display: flex;
    flex-direction: column;
    align-content: center;
    margin: auto;
    width: 80%;

    /* border-width: 1px;
    
    border-color: #9d9d9d !important; */
    border: 3px solid #9d9d9d;
    border-radius: 20px;
    background-color: #e9e9e9;
  }
  #aboutTitle {
    margin-top: 1em;
    margin-bottom: 2em;
    height: 5em;
    padding: 0;
  }
  #featuresDiv {
    margin: auto;
    margin-top: 4em;
    /* text-align: left; */
    font-size: 1.5em;
    font-weight: 200;
  }
  #npmdownloadcontainer {
    margin: auto;
    margin-top: 3em;
    margin-bottom: 3em;
    padding-top: 1em;
    padding-bottom: 0.75em;
    width: 15%;
    border: 2px solid #9d9d9d;
    border-radius: 20px;
    background-color: #f9f9f9;
  }
  /* p {
    margin-top: 30px;
    text-align: center;
    padding-left: 200px;
    padding-right: 200px;
    font-size: 1.5em;
    font-weight: 200;
  } */
  span {
    cursor: pointer;
  }
  span:hover {
    color: #6194bc;
  }
  /* ul {
    margin: '200px, 10px, 20px, 100px';
    align-items: left; */
  /* list-style-image: url({cloud}); */
  /* } */
</style>
