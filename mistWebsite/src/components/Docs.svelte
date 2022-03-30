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
    <h3>Navigation</h3>
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
        ## App Setup ## `App.svelte` This serves as the top level component, and
        our primary page for the application, rendering core components of
        `Worker`, the Mist title and the dark mode toggle button `Dark Button`.
        ## Script In the script tag, components and theme details are imported
        to work with. The toggle function for dark mode is declared as well. ##
        Body In the body of this .svelte file, the components are structured and
        setup to be rendered upon page load. ## Style In the style tags, our
        theme and visual element specifications are defined. ## `main.js` This
        is the entry point of our application. The `App.svelte` component is
        imported, instantiated, binded to the HTML document body, and exported.
        # `store.js` Here, our application's core reactive variables, and
        visualization data variables are declared and held. We import the
        `writable` method from `svelte/store` to provide access to Svelte's
        store and state management functionality. Each variable is exported from
        this JS file, so that it is usable in our other files and components.
        Variables that we want to be reactive to document activity include the
        writable method. Our variables that hold chart creation data points are
        not reactive, as they are updated via our `functions.js` file already.
      </p>
    </div>
    <div id="navFunctions" class="docsSec">
      <h3>Functions</h3>
      <p>
        ## functions.js ## Imports First, the Chart functionality from
        `chart.js` is imported. Next, the variables required to generate data
        are imported from the store.js file. ## `createData` The function that
        is defined here generates the data required for population of the
        scatter chart, pie chart and bar graph. The chart data is also reset via
        the reassignment of data variables to 0. Note - this function is not
        invoked here, but instead in `Worker.svelte` The `createData` function
        takes in parameters of logs and avgLogs which contain the backend data
        we require. We use the duration data to generate y-axis plot points for
        length of duration on the scatter chart. We use the status code data to
        categorize our y-axis plot points in the scatter chart, and additionally
        for the population of our Pie Chart data that provides a breakout
        summary of function Successes and Failures. We use the `avgLogs` data to
        generate the average duration of the functions we ran analytics on, for
        each of the previous 5 sessions. ## `createScatterChart` This function
        uses the data variables (succs, errs, labels) to define the dataset and
        styling details to be used in the chart configuration. Constant `config`
        utilizes Chart.js documentation guidelines to create the configuration
        and chart details such as axes, labels, gridlines and sizing. Constant
        `scatterChart` creates the chart and connects it to the document element
        `scatterChart`. ## `createPieChart` This function uses the data
        variables (pieData, pieLabels) to define the dataset and styling details
        that are used in the chart configuration. The configuration details
        based on Chart.js documentation guidelines are defined in const
        `config`. Const `doughnutChart` creates the chart and connects it to the
        document element `doughnutChart`. # `createBarGraph` This function uses
        the data variables (sessNums, sessAvgs) to define the dataset and
        styling details that are used in the chart configuration. The
        configuration details based on Chart.js documentation guidelines are
        defined in const `config`. Const `barGraph` creates the chart and
        connects it to the document element `barGraph`.
      </p>
    </div>
    <div id="navsvelteComponents" class="docsSec">
      <h3>Svelte Components</h3>
      <p>
        ## Svelte Components Inside of the src/components directory, we hold the
        Svelte files that create our page's reactive and reusable components. ##
        `Worker.svelte` Here, we define the core page structure of our analytics
        visualization, along with the connectivity to the server and database
        info retrieval, that gets displayed on the dashboard. ## Script We begin
        by importing each modularized chart component, reactive variables from
        `store.js`, and data/chart creation functionality from `functions.js`.
        The variables `workerTimer`, `chartFlag` and `mockLogArray` are marked
        reactive by the `$:` syntax. ## `start` The functionality to mark the
        beginning of data collection and retrieve the session number from our
        server/database is defined here. ## `stop` The functionality to mark the
        end of data collection, and retrieve the sessionLogs data is defined
        here. This data is used to create the `mockLogArray` which is utilized
        in the creation of duration and status data for our charts. A second
        fetch request obtains the information to populate the `mockAvgsArray`
        for our previous 5 session info graph. ## `chart` Here, the chart data
        is created, and each chart that displays data for the worker is created.
        An initial check is in place to validate that any recent data has been
        reset prior to another session of data collection. ## `resetChart` The
        functionality for resetting chart data is located here. ## Body The page
        structure of chart text, component layout, along with buttons are
        defined, and conditional rendering settings are created here. ## Style
        Start button status color updates, and Pie Chart sizing and styling
        details are set. ## `DarkButton.svelte` The toggle button for dark mode
        is defined, and styling for the button are establised. ## `Table.svelte`
        The `mockLogArray` data for table population is imported from
        `store.js`. The table structure and looping mechanism through
        `mockLogArray` to populate the table with the number of functional
        metrics objects received is performed, along with general styling. ##
        Charts In each of the svelte files for `ScatterChart`, `PieChart` and
        `BarGraph` the chart is instantiated onto a canvas element with it's
        relevant id, and fundamental style structure is setup.
      </p>
    </div>
    <div id="navserver" class="docsSec">
      <h3>Server</h3>
      <p>
        # server.js overview ## `PORT` Our port is set to localhost:3000. ##
        `app.post('/allData',
        metricsController.siftMetrics,metricsController.addMetrics,)` After
        editing the **_Miniflare_** npm file, data from any requests sent to the
        **_Miniflare_** server will be sent in the body of a POST request to
        this route on the **_mist_** server. The request is directed to the
        metricsController where the siftMetrics method converts the data into
        the proper format for the database, and the addMetrics method posts the
        data to the user's SQL database. ## `app.get('/sessionNum',
        metricsController.getSessionNum)` This function is invoked when a user
        presses "start" on the front-end. It routes to
        metricsController.getSessionNum middleware. This function responds with
        a string confirming that the sessionNum has been set. ##
        `app.get('/sessionLogs', metricsController.getSessionLogs)` The
        metricsController.getSessionLogs middleware is invoked when a user
        presses 'stop' on the front-end. This sends a GET request to the
        '/sessionLogs' endpoint and a query is sent to the database. This query
        retrieves all the metrics associated with the current sessionNum and
        stores them in res.locals. Once the metrics are stored we return a
        response back to the frontend with our res.locals.logs json parsed. ##
        `app.use('/\*')` Here we have a catch-all route handler for requests
        made to an unknown route. ## `app.use` Finally, we have a error handler
        for any errors that occur during middleware invocations.
      </p>
    </div>
    <div id="navmetrics" class="docsSec">
      <h3>Metrics Controller</h3>
      <p>
        # metricsController.js Here, the middleware is defined. ##
        `metricsController` Controller holds all of our middleware
        (getSessionNum, getSessionLogs, siftMetrics and addMetrics). The key
        'sessionNum' has a value that is equal to the current session number and
        defaults to 1. ## `getSessionNum` This middleware is invoked when a dev
        presses "start" on the front-end. Our **database query** looks up the
        highest stored sessionNum, which corresponds to the last recorded
        session, and incremenets that integer by 1. A session is defined as data
        collected from when a dev clicks **start** until they click **stop**.
        The sessionNum is stored in our metricsController and is defaulted to
        one for new devs. This property will be used later by siftMetrics. ##
        `getSessionLogs` This middleware is invoked when a dev presses "stop" on
        the front-end of **_mist_**. A query is sent to the database that
        selects all logs from the current session. This data is saved in an
        array of objects on res.locals.logs. ## `siftMetrics` This middleware
        destructures the method, URL, status, and response time data from the
        POST request body. These data points are saved in a 'metrics' object;
        response time is converted into a unit-less number before being saved.
        This controller also captures the current session number and the time
        that the request hits the controller and saves both data points in the
        metrics object. ## `addMetrics` The addMetrics middleware is triggered
        after the metricsController.siftMetrics middleware executes and saves
        metrics data in an object called 'metrics' in 'res.locals.metrics'. Once
        we are in the addMetrics middleware, res.locals.metrics is destructured
        and the data that we gathered is injected into an SQL query and saved in
        the user database.
      </p>
    </div>
    <div id="navdatabase" class="docsSec">
      <h3>Database</h3>
      <p>
        # Database ## db_template.sql This file allows users to create an
        instance of a SQL database that matches our template. The user must
        first set up their own postgresQL database and then carry out the
        terminal commands from the README to forge the link. All of the SQL
        commands in this file will be executed on their database, creating the
        **metrics** table with the appropriate columns. ## metrics_model.js This
        is where the user inputs the URI of the postgresQL database they
        created. The user will have used our db_template.sql to instantiate a
        SQL database that contains our metrics table. Our **metrics_model** is
        exported and then imported in the metricsController.js file.
      </p>
    </div>
    <p>Yes</p>
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
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
    <p>cool info here</p>
  </section>
</article>

<style>
  h3 {
    font-weight: 300;
  }
  article {
    display: flexbox;
    justify-content: space-between;
  }
  /* p {
    cursor: pointer;
  } */
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
    margin-left: 10em;
    text-align: left;
  }
</style>
