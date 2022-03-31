<script>
  const startBtn = './images/gifs/startbtn.gif';
  const stopBtn = './images/gifs/stopbtn.gif';
  const genMetBtn = './images/gifs/generateMetricsbtn.gif';
  const resMetBtn = './images/gifs/resetMetricsbtn.gif';
  const sql = './images/gifs/sql.gif';
  const npmgif = './images/gifs/npm.gif';
  const startApp = './images/gifs/startApp.gif';
</script>

<article id="tut">
  <div id="tutTitle">
    <h1>Tutorial</h1>
  </div>
  <section class="tutSection">
    <div class="tutText">
      <h2>Getting Started</h2>
      <p>
        Clone this repo into your local machine in the same directory where the
        worker you want to test is located. <code
          >git clone https://github.com/oslabs-beta/mist.git</code
        >
        <br />
        <br />
        Grab the npm package download text for mist-analytics
        <br />

        <br />
        <br />
        Install the dependencies in the cli by running <code>npm install</code>
        <br />
        <br />
        Create a .env file in the root of the mist directory
      </p>
    </div>
    <div class="tutGif">
      <img src={npmgif} alt="tutorial gif" style="height: 400px;" />
    </div>
  </section>
  <section class="tutSection">
    <div class="tutText" style="height: 400px;">
      <h2>Database Setup</h2>
      <p>
        Set up a postgreSQL database (we recommend using elephantSQL) and link
        it to the SQL schema
        <br />
        <br />
        - Copy the link to your empty database
        <br />
        - Paste that link into the ENV file and save it as myURI
        <br />
        - Open up the mist directory in your terminal
        <br />
        - Run the following command:
        <code>psql -d [url from elephantSQL] -f db_template.sql</code>
      </p>
    </div>
    <div class="tutGif" style="height: 400px;">
      <img src={sql} alt="tutorial gif" style="height: 450px;" />
    </div>
  </section>
  <section class="tutSection">
    <div class="tutText">
      <h2>Start up App</h2>
      <p>
        To start up the app, and prepare for a session recording, Run the
        following scripts:
        <br />
        <br />
        - <code>npm run dev</code> to start the GUI on localhost:8080
        <br />
        - <code>node server/server.js</code> to start the server listening on
        your worker
        <br />
        - <code>node --require './server/tracing.js' server/miniflare</code> to start
        your worker
      </p>
    </div>
    <div class="tutGif">
      <img
        src={startApp}
        alt="tutorial gif"
        style="height: 450px; overflow: hidden; float: bottom;"
      />
    </div>
  </section>
  <section class="tutSection">
    <div class="tutText">
      <h2>Start Button</h2>
      <p>
        The Start button begins the recording session. It sets a point via the
        web API <code>Date.now()</code> function against which requests made to the
        worker will be plotted. Run your worker after pressing start.
      </p>
    </div>
    <div class="tutGif">
      <img src={startBtn} alt="tutorial gif" />
    </div>
  </section>
  <section class="tutSection">
    <div class="tutText">
      <h2>Stop Button</h2>
      <p>
        The Stop button ends the recording session. It sets a point via the web
        API <code>Date.now()</code> function marking the completion of the recording
        session. Any worker requests made after the stop button is pressed will not
        be plotted, so be sure to press the stop button only once you have completed
        running your worker.
      </p>
    </div>
    <div class="tutGif">
      <img src={stopBtn} alt="tutorial gif" />
    </div>
  </section>
  <section class="tutSection">
    <div class="tutText">
      <h2>Generate Metrics</h2>
      <p>
        The Generate Metrics button processes the recorded worker
        request/response logs, calculating datasets to be fed to the charting
        library. After a couple of seconds the metrics will render to the page,
        providing the following:<br /> <br />
        &ensp ➡️ &ensp A <span style="color: #6194bc;">table</span> displaying
        each request log <br />
        &ensp ➡️ &ensp A <span style="color: #6194bc;">scatter chart</span>
        visualizing the recording session <br />
        &ensp ➡️ &ensp A <span style="color: #6194bc;">pie chart</span>
        visualizing total successes and errors <br />
        &ensp ➡️ &ensp A <span style="color: #6194bc;">bar graph</span>
        visualizing the average response time from the previous five recording sessions
        <br />
      </p>
    </div>
    <div class="tutGif">
      <img src={genMetBtn} alt="tutorial gif" />
    </div>
  </section>
  <section class="tutSection">
    <div class="tutText">
      <h2>Reset Metrics</h2>
      <p>
        The Reset Metrics button clears Mist's local store of processed log
        data, and removes the visualizations from the application to ready it
        for the next recording session.
      </p>
    </div>
    <div class="tutGif">
      <img src={resMetBtn} alt="tutorial gif" />
    </div>
  </section>
  <!-- <section class="tutSection">
    <div class="tutText">
      <h2>Troubleshooting</h2>
      <p>Maybe we get rid of this</p>
    </div>
    <div class="tutGif">
      <img href="#" alt="tutorial gif" />
    </div>
  </section> -->
</article>

<style>
  /* #tutGettingStarted {
    margin-left: 3em;
    margin-right: 3em;
    margin: auto;
    width: 100%;
    outline: 2px solid #9d9d9d;
    border-radius: 20px;
    margin-top: 1em;
  } */
  #tut {
    display: flex;
    flex-direction: column;
  }
  #tutTitle {
    margin: auto;
    margin-bottom: 5em;
    height: 5em;
  }
  .tutSection {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-top: 5em;
  }
  .tutText {
    display: flex;
    flex-direction: column;
    width: 50%;
    text-align: left;
    outline: 2px solid #9d9d9d;
    border-radius: 20px;
    padding: 1em;
    margin-left: 7em;
    background-color: #e9e9e9;
  }
  /* .tutText p {
      
  } */
  .tutGif {
    margin-right: 7em;
    outline: 2px solid #9d9d9d;
    border-radius: 20px;
    width: 25%;
    background-color: #e9e9e9;
    overflow: hidden !important;
  }
  code {
    font-size: 200;
    outline: 1px solid #b3b3b3;
    border-radius: 3px;
    background-color: #f9f9f9;
  }
</style>
