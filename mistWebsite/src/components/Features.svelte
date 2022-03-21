<script></script>

<div>
  <h1>Features</h1>
  <h2>Start Button</h2>
  <p>
    Start button 'on click' sends a fetch request to the user's linked SQL
    database. The fetch request sends a custom query to get the users current
    session number.
  </p>
  <h2>Stop Button</h2>
  <p>
    Stop Button 'on click' sends a SQL query that gathers all metric data from
    the users metric table in their SQL database where the session number is
    equal to the current session number.
  </p>
  <h2>Generate Metrics</h2>
  <h2>Clear Metrics</h2>
</div>

<style>
  p {
    /* color: blue; */
    text-align: left;
    padding-left: 10px;
  }
  div {
    margin: auto;
    width: 95%;
    border-width: 1px;
    border-radius: 20px;
    border-color: grey;
    border: solid;
    margin-top: 20px;
    margin-bottom: 20px;
  }
  h1 {
    /* color: blue; */
  }
  h2 {
    text-align: left;
    padding-left: 10px;
    color: blue;
    font-size: 2em;
  }
</style>
