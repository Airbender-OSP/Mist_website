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
        declared. In the body of this <code>.svelte</code> file, the components
        are structured and setup to be rendered upon page load. The theme and
        visual element specifications are defined in the style tags.
        <br />
        <br />
        <span class="bold">Main JS</span>
        <br />
        <code>main.js</code> is the entry point of our application. The
        <code>App.svelte</code>
        component is imported, instantiated, and bound to the HTML document body.
        An export is established in order to append the rest of Mist's GUI to this
        file.
        <br />
        <br />
        <span class="bold">Store</span>
        <br />
        Here in <code>store.js</code>, Mist's core reactive variables and
        visualization data variables are declared and held. The
        <code>writable</code>
        method from
        <code>svelte/store</code> is imported to provide access to Svelte's
        store and state management functionality. Each variable is exported from
        this JS file to be usable in Mist's other files and components.
        Variables that are to be reactive to document activity include the
        writable method. The variables that hold chart creation data points are
        not reactive, as they are updated via the <code>functions.js</code>
        file.
      </p>
    </div>
    <div id="navFunctions" class="docsSec">
      <h3>Functions</h3>
      <p>
        <span class="bold">Imports</span>
        <br />
        In <code>functions.js</code> the Chart functionality from
        <code>chart.js</code>
        is imported. Next, the variables required to generate data are imported from
        the <code>store.js</code>
        file.
        <br />
        <br />
        <span class="bold">Create Data</span>
        <br />
        <code>createData</code> - This function generates the data required for
        population of the scatter chart, pie chart, and bar graph. The chart
        data is also reset during invocation. Note - this function is invoked
        only in <code>Worker.svelte</code>.
        <code>createData</code>
        accepts the parameters <code>logs</code>
        and <code>avgLogs</code> which contain the backend data retreived from a
        recording session. The duration of the recording session generates
        x-axis plot points on the scatter chart. The status code, start time,
        and response time from the recorded <code>logs</code> are used to
        categorize the y-axis plot points in the scatter chart, and additionally
        for the population of the Pie Chart's summary of response Successes and
        Errors. The <code>avgLogs</code> data is used to generate the average
        duration of the request response times recorded for each of the previous
        5 recording sessions.
        <br />
        <br />
        <span class="bold">Charting Functions</span>
        <br />
        <code>createScatterChart</code> - References the data variables
        <code>succs</code>, <code>errs</code>, and <code>labels</code> to define
        the dataset used by the scatter chart. The configuration details
        established in the Chart.js documentation guidelines are defined in the
        constant variable
        <code>config</code>. The constant variable
        <code>scatterChart</code>
        creates the chart and attaches it to the
        <code>ScatterChart.svelte</code>
        component.
        <br />
        <br />
        <code>createPieChart</code> - References the variables
        <code>pieData</code>
        and <code>pieLabels</code> to define the dataset used in chart
        configuration. The configuration details established in the Chart.js
        documentation guidelines are defined in the constant variable
        <code>config</code>. The constant variable <code>doughnutChart</code>
        creates the chart and attaches it to the <code>PieChart.svelte</code>
        component.
        <br />
        <br />
        <code>createBarGraph</code> - References the data variables
        <code>sessNums</code>
        and <code>sessAvgs</code> to define the dataset and styling details used
        in chart configuration. The configuration guidelines established in the
        Chart.js documentation are stored in the constant variable
        <code>config</code>. The constant variable <code>barGraph</code> creates
        the chart and attaches it to the <code>BarGraph.svelte</code> component.
      </p>
    </div>
    <div id="navsvelteComponents" class="docsSec">
      <h3>Svelte Components</h3>
      <p>
        Mist's Svelte components are inside the <code>src/components</code>
        directory.
        <br />
        <br />
        <span class="bold">Worker</span>
        <br />
        <code>Worker.svelte</code> - Defines the core page structure of Mist,
        along with connectivity to the server and database. Modularized chart
        components, reactive variables from <code>store.js</code>, and
        data/chart creation functionality from <code>functions.js</code> is
        imported in script. The variables
        <code>workerTimer</code>, <code>chartFlag</code>, and
        <code>mockLogArray</code> are marked reactive by the <code>$</code>
        syntax.
        <br />
        <br />
        <span class="bold">Functions</span>
        <br /> <code>start</code> - Defines the functionality marking the
        beginning of data collection and retrieves the session number from the
        database.
        <br /> <code>stop</code> - Defines the functionality marking the end of
        data collection, and retrieves the <code>sessionLogs</code>. This data
        is used to generate the <code>mockLogArray</code> which is utilized in
        the creation of data for our charts. A second fetch request obtains the
        information to populate the <code>mockAvgsArray</code> for the bar graph
        displaying the average response time of the previous 5 recording
        sessions.
        <br /> <code>chart</code> - Chart data is generated via
        <code>createData</code>, which is the utilized by the chart creation
        functions that follow. An initial check is in place to validate that any
        recent data has been reset prior to another session of data collection.
        <br /> <code>resetChart</code> - Defines the functionality for resetting
        chart data.
        <br />
        <br />
        <span class="bold">Main/Style</span>
        <br />
        <code>Body</code> defines the page structure of chart text, component
        layout, and buttons. Conditional rendering settings are also defined
        here. The style tag contains the dynamic start button color shading, and
        Pie Chart sizing details are set.
        <br />
        <br />
        <span class="bold">Components</span>
        <br /> <code>DarkButton.svelte</code> - Defines the styling for the dark
        mode toggle button.
        <br /> <code>Table.svelte</code> - <code>mockLogArray</code> is imported
        from <code>store.js</code>, and then iterated over to populate the
        table. The style tag defines the appearance of the generated table.
        <br />
        <br />
        <span class="bold">Charts</span>
        <br />
        In each of the svelte files for <code>ScatterChart</code>,
        <code>PieChart</code>
        and <code>BarGraph</code>
        the chart is instantiated onto a canvas element with the relevant id.
      </p>
    </div>
    <div id="navserver" class="docsSec">
      <h3>Server</h3>
      <p>
        <code>PORT</code> - Mist's server port is set to localhost:3000. <br />
        <br />
        <span class="bold">Route Details</span>
        <br />
        <code
          >app.use('/v1/traces', metricsController.siftMetrics,
          metricsController.addMetrics)</code
        >
        - When the tracing on ***Miniflare*** is complete, the data is exported to
        the server. It is routed through the
        <code>metricsController.siftMetrics</code>
        middleware and then the <code>metricsController.addMetrics</code>
        middleware to access the needed parts of the trace and post the data to the
        postgreSQL database.
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
        a response is returned with an updated
        <code>res.locals.logs</code> and parsed.
        <br />
        <br />
        <code>app.use('/\*')</code> - A catch-all handler for requests made to
        unknown routes.
        <br />
        <br />
        <code>app.use</code> - An error handler for any errors that occur during
        middleware invocations.
      </p>
    </div>
    <div id="navmetrics" class="docsSec">
      <h3>Metrics Controller</h3>
      <p>
        Middleware is defined inside the controller. <br />
        <br />
        <code>metricsController</code> - Contains all of Mist's middleware (<code
          >getSessionNum</code
        >,
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
        is received by the controller, and saves both data points in the
        <code>metrics</code>
        object. <br />
        <br />
        <code>addMetrics</code> - This middleware is triggered after the
        <code>metricsController.siftMetrics</code>
        middleware executes and saves metrics data in an object called
        <code>metrics</code>
        in <code>res.locals</code>. Once in the <code>addMetrics</code>
        middleware, <code>res.locals.metrics</code>
        is destructured and the gathered data is injected into an SQL query and saved
        in the user database.
      </p>
    </div>
    <div id="navdatabase" class="docsSec">
      <h3>Database</h3>
      <p>
        <code>db_template.sql</code> - This file allows users to create an
        instance of a SQL database that matches Mist's template. The user must
        first set up their own postgresQL database and then carry out the
        terminal commands from the <code>README</code>
        to forge the link. All of the SQL commands in this file will be executed
        on their database, creating the *metrics* table with the appropriate columns.
        <br />
        <br />
        <code>metrics_model.js</code> - Here the user inputs the URI of the
        postgreSQL database they created. The user will have used
        <code>db_template.sql</code>
        to instantiate a SQL database that contains Mist's metrics table. The
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
