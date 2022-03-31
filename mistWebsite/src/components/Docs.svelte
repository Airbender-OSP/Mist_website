<script>
  //   let elem = document.querySelector('p');
  //   let rect = elem.getBoundingClientRect();
  const navToggle = (e) => {
    // alert(`${e.target.id}`);
    document.getElementById(`nav${e.target.id}`).scrollIntoView();
  };
</script>

<article>
  <section id="documentationNav">
    <h3 style="font-weight: 100; color: #6194bc">Navigation</h3>
    <div>
      <a id="appSetup" style="cursor: pointer" on:click={(e) => navToggle(e)}>
        App Setup
      </a>
      <br />
      <br />
    </div>
    <div>
      <a id="Functions" style="cursor: pointer" on:click={(e) => navToggle(e)}>
        Functions
      </a>
      <br />
      <br />
    </div>
    <div>
      <a
        id="svelteComponents"
        style="cursor: pointer"
        on:click={(e) => navToggle(e)}
      >
        Svelte Components
      </a>
      <br />
      <br />
    </div>
    <div>
      <a id="server" style="cursor: pointer" on:click={(e) => navToggle(e)}>
        Server
      </a>
      <br />
      <br />
    </div>
    <div>
      <a id="metrics" style="cursor: pointer" on:click={(e) => navToggle(e)}>
        Metrics Controller
      </a>
      <br />
      <br />
    </div>
    <div>
      <a id="database" style="cursor: pointer" on:click={(e) => navToggle(e)}>
        Database
      </a>
      <br />
      <br />
    </div>
  </section>
  <section id="documentation">
    <h1>DOCUMENTATION</h1>
    <div id="navappSetup" class="docsSec">
      <h3>App Setup</h3>
      <p>
        <span class="bold">Svelte App</span>
        <br />
        In the <code>App.svelte</code> file we serve as the top level component,
        and our primary page for the application, rendering the core components
        of <code>Worker.svelte</code>, the Mist title, and the Dark Mode toggle
        button <code>DarkButton.svelte</code>. In the script tag, components and
        theme details are imported, and the toggle function for dark mode is
        declared. In the body of this .svelte file, the components are
        structured and setup to be rendered upon page load. In the style tags,
        our theme and visual element specifications are defined.
        <br />
        <br />
        <span class="bold">Main JS</span>
        <br />
        The <code>main.js</code> is the entry point of our application. The
        <code>App.svelte</code>
        component is imported, instantiated, bound to the HTML document body, and
        exported.
        <br />
        <br />
        <span class="bold">Store</span>
        <br />
        Here in <code>store.js</code>, our application's core reactive variables
        and visualization data variables are declared and held. We import the
        <code>writable</code>
        method from
        <code>svelte/store</code> to provide access to Svelte's store and state
        management functionality. Each variable is exported from this JS file so
        that it is usable in our other files and components. Variables that we
        want to be reactive to document activity include the writable method.
        Our variables that hold chart creation data points are not reactive, as
        they are updated via our <code>functions.js</code>
        file already.
      </p>
    </div>
    <div id="navFunctions" class="docsSec">
      <h3>Functions</h3>
      <p>
        <span class="bold">Imports</span>
        <br />
        In <code>functions.js</code>, first the Chart functionality from
        <code>chart.js</code>
        is imported. Next, the variables required to generate data are imported from
        the <code>store.js</code>
        file.
        <br />
        <br />
        <span class="bold">Create Data</span>
        <br />
        The <code>createData</code> function that is defined here generates the
        data required for population of the scatter chart, pie chart and bar
        graph. The chart data is also reset via the reassignment of data
        variables to 0. Note - this function is not invoked here, but instead in
        <code>Worker.svelte</code>. This function takes in parameters of
        <code>logs</code>
        and <code>avgLogs</code> which contain the backend data we from a
        recording session. We use the duration of the recording session to
        generate x-axis plot points on the scatter chart. We use the status
        code, start time, and response time from the recorded <code>logs</code>
        to categorize our y-axis plot points in the scatter chart, and additionally
        for the population of our Pie Chart's summary of response Successes and Errors.
        We use the <code>avgLogs</code> data to generate the average duration of
        the request response times recorded for each of the previous 5 recording
        sessions.
        <br />
        <br />
        <span class="bold">Charting Functions</span>
        <br />
        The <code>createScatterChart</code> function uses the data variables
        (succs, errs, labels) to define the dataset and styling details to be
        used in the chart configuration. Constant <code>config</code> utilizes
        Chart.js documentation guidelines to create the configuration and chart
        details such as axes, labels, gridlines and sizing. Constant
        <code>scatterChart</code>
        creates the chart and connects it to the
        <code>ScatterChart.svelte</code>
        component.
        <br />
        <br />
        The <code>createPieChart</code> function uses the data variables (<code
          >pieData</code
        >, <code>pieLabels</code>) to define the dataset and styling details
        that are used in the chart configuration. The configuration details
        based on Chart.js documentation guidelines are defined in const
        <code>config</code>. Const <code>doughnutChart</code> creates the chart
        and connects it to the <code>doughnutChart.svelte</code> component.
        <br />
        <br />
        The <code>createBarGraph</code> function uses the data variables (<code
          >sessNums</code
        >, <code>sessAvgs</code>) to define the dataset and styling details that
        are used in the chart configuration. The configuration details based on
        Chart.js documentation guidelines are defined in const
        <code>config</code>. Const <code>barGraph</code> creates the chart and
        connects it to the <code>BarGraph.svelte</code> component.
      </p>
    </div>
    <div id="navsvelteComponents" class="docsSec">
      <h3>Svelte Components</h3>
      <p>
        Svelte Components Inside of the <code>src/components</code>
        directory, we hold the Svelte files that create our page's reactive and reusable
        components.
        <br />
        <br />
        <span class="bold">Worker</span>
        <br />
        In <code>Worker.svelte</code> we define the core page structure of our
        analytics visualization, along with the connectivity to the server and
        database info retrieval, that gets displayed on the dashboard. In script
        we begin by importing each modularized chart component, reactive
        variables from <code>store.js</code>, and data/chart creation
        functionality from <code>functions.js</code>. The variables
        <code>workerTimer</code>, <code>chartFlag</code> and
        <code>mockLogArray</code> are marked reactive by the <code>$:</code>
        syntax.
        <br />
        <br />
        <span class="bold">Functions</span>
        <br /> <code>start</code> - The functionality to mark the beginning of
        data collection and retrieve the session number from our server/database
        is defined here.
        <br /> <code>stop</code> - The functionality to mark the end of data
        collection, and retrieve the sessionLogs data is defined here. This data
        is used to create the mockLogArray which is utilized in the creation of
        duration and status data for our charts. A second fetch request obtains
        the information to populate the mockAvgsArray for our previous 5 session
        info graph.
        <br /> <code>chart</code> - Here, the chart data is created, and each
        chart that displays data for the worker is created. An initial check is
        in place to validate that any recent data has been reset prior to
        another session of data collection.
        <br /> <code>resetChart</code> - The functionality for resetting chart
        data is located here.
        <br />
        <br />
        <span class="bold">Main/Style</span>
        <br />
        In body, the page structure of chart text, component layout, and buttons
        are defined. Conditional rendering settings are also created here. In style
        the start button status color updates, and Pie Chart sizing and styling details
        are set.
        <br />
        <br />
        <span class="bold">Components</span>
        <br /> <code>DarkButton.svelte</code> - The toggle button for dark mode
        is defined, and styling for the button are establised.
        <br /> <code>Table.svelte</code> - The <code>mockLogArray</code> data
        for table population is imported from <code>store.js</code>. The table
        structure and looping mechanism through <code>mockLogArray</code> to
        populate the table with the number of functional metrics objects
        received is performed, along with general styling.
        <br />
        <br />
        <span class="bold">Charts</span>
        <br />
        In each of the svelte files for <code>ScatterChart</code>,
        <code>PieChart</code>
        and <code>BarGraph</code>
        the chart is instantiated onto a canvas element with it's relevant id, and
        fundamental style structure is established.
      </p>
    </div>
    <div id="navserver" class="docsSec">
      <h3>Server</h3>
      <p>
        <code>PORT</code> - Our port is set to localhost:3000. <br />
        <br />
        <span class="bold">Route Details</span>
        <br />
        <code
          >app.use('/v1/traces', metricsController.siftMetrics, metricsController.addMetrics)</code>
        - When the tracing on ***Miniflare*** is complete, the data is exported to the server. It is routed through the <code>metricsController.siftMetrics</code> middleware and then the <code>metricsController.addMetrics</code> middleware to access the needed parts of the trace and post the data to the postgreSQL database, respectively.
        <br />
        <br />
        <code>app.get('/sessionNum', metricsController.getSessionNum)</code> -
        This function is invoked when a user presses <code>Start</code> on the
        GUI. It routes to <code>metricsController.getSessionNum</code>
        middleware. This function responds with a string confirming that the
        <code>sessionNum</code>
        has been set. <br />
        <br />
        <code>app.get('/sessionLogs', metricsController.getSessionLogs)</code> -
        The <code>metricsController.getSessionLogs</code>
        middleware is invoked when a user presses <code>Stop</code> on the GUI.
        This sends a GET request to the '/sessionLogs' endpoint, and a query is
        sent to the database. This query retrieves all of the metrics associated
        with the current <code>sessionNum</code>
        and stores them in <code>res.locals</code>. Once the metrics are stored
        we return a response back to the frontend with our
        <code>res.locals.logs</code>
        json parsed. <br />
        <br />
        <code>app.use('/\*')</code> - Here we have a catch-all route handler for
        requests made to an unknown route.
        <br />
        <br />
        <code>app.use</code> - Finally, we have a error handler for any errors that
        occur during middleware invocations.
      </p>
    </div>
    <div id="navmetrics" class="docsSec">
      <h3>Metrics Controller</h3>
      <p>
        Here, the middleware is defined inside of the controller <br />
        <br />
        <code>metricsController</code> - the controller holds all of our
        middleware (<code>getSessionNum</code>,
        <code>getSessionLogs</code>, <code>siftMetrics</code> and
        <code>addMetrics</code>). The key <code>sessionNum</code> has a value
        that is equal to the current session number and defaults to 1.<br />
        <br />
        <code>getSessionNum</code> - This middleware is invoked when a dev
        presses <code>Start</code> on the GUI. Our database query looks up the
        highest stored <code>sessionNum</code>, which corresponds to the last
        recorded session, and incremenets that integer by 1. A session is
        defined as data collected from when a dev clicks <code>Start</code>
        until <code>Stop</code> is pressed. The <code>sessionNum</code> is
        stored in our <code>metricsController</code>
        and is defaulted to one. This property will be used later by
        <code>siftMetrics</code>. <br />
        <br />
        <code>getSessionLogs</code> - This middleware is invoked when a dev
        presses <code>Stop</code> on the GUI. A query is sent to the database
        that selects all logs from the current session. This data is saved in an
        array of objects on <code>res.locals.logs</code>.
        <br />
        <br />
        <code>siftMetrics</code> - This middleware destructures the method, URL,
        status, and response time data from the POST request body. These data
        points are saved in a <code>metrics</code> object; response time is
        converted into a unit-less number before being saved. This controller
        also captures the current session number and the time that the request
        is received by the controller and saves both data points in the
        <code>metrics</code>
        object. <br />
        <br />
        <code>addMetrics</code> - This middleware is triggered after the
        <code>metricsController.siftMetrics</code>
        middleware executes and saves metrics data in an object called
        <code>metrics</code>
        in <code>res.locals.metrics</code>. Once in the <code>addMetrics</code>
        middleware, <code>res.locals.metrics</code>
        is destructured and the gathered data is injected into an SQL query and saved
        in the user database.
      </p>
    </div>
    <div id="navdatabase" class="docsSec">
      <h3>Database</h3>
      <p>
        <code>db_template.sql</code> - This file allows users to create an
        instance of a SQL database that matches our template. The user must
        first set up their own postgresQL database and then carry out the
        terminal commands from the <code>README</code>
        to forge the link. All of the SQL commands in this file will be executed
        on their database, creating the *metrics* table with the appropriate columns.
        <br />
        <br />
        <code>metrics_model.js</code> - This is where the user inputs the URI of
        the postgreSQL database they created. The user will have used our
        <code>db_template.sql</code>
        to instantiate a SQL database that contains our metrics table. Our
        <code>metrics_model</code>
        is exported, and then imported to the <code>metricsController.js</code> file.
      </p>
    </div>
    <!-- <p>Yes</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p> -->
    <!-- <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p> -->
  </section>
</article>

<style>
  h3 {
    font-weight: 400;
  }
  a {
    font-weight: 100;
  }
  a:hover {
    color: #6194bc;
  }
  article {
    display: flexbox;
    justify-content: space-between;
  }
  /* p { */
  /* text-align: left; */
  /* } */
  .bold {
    font-weight: 300;
  }
  #documentationNav {
    /* border-right: 3px solid #9d9d9d; */

    width: 15%;
    position: fixed;
    height: 100%;
  }
  #documentation {
    width: 80%;
    float: right;
    background-color: #e9e9e9;
    border-radius: 20px;
    border: 3px solid #9d9d9d;
  }
  .docsSec {
    margin-top: 5em;
    padding-top: 10px;
    margin-left: 3em;
    margin-right: 3em;
    text-align: left;
    outline: 2px solid #9d9d9d;
    border-radius: 20px;
    padding: 1em;
    background-color: #f9f9f9;
  }
  code {
    font-size: 200;
    outline: 1px solid #b3b3b3;
    border-radius: 3px;
    background-color: #e9e9e9;
  }
</style>
