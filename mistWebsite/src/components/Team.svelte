<script>
  /* import assets from './assets'; */
  import MaterialButton from './MaterialButton.svelte';
  let anthony = '/images/Anthony.jpg';
  let eric = '/images/Eric.jpg';
  let kristen = '/images/Kristen.png';
  let leo = '/images/Leo.jpeg';
  let stew = '/images/Stew.png';
  let linkedInIcon = '/images/linkedIn.png';
  let gmailIcon = '/images/gmail.png';
  let githubIcon = '/assets/github120.png';
</script>

<div>
  <h1>Meet The Team!</h1>
</div>

<div class="row">
  <div class="column">
    <div class="card">
      <img src={anthony} alt="Anthony" style="width:100%" />
      <div class="container">
        <h2>Anthony Marin</h2>
        <p class="title">Software Engineer</p>
        <MaterialButton
          class="github"
          id="antGH"
          icon={githubIcon}
          text="Github"
          onClickFunction={() => {
            window.open('github.com/anthonymarinated');
          }}
        />

        <MaterialButton
          class="linkedin"
          id="antLI"
          text="LinkedIn"
          icon={linkedInIcon}
          onClickFunction={() => {
            window.open('https://www.linkedin.com/in/anthmari/');
          }}
        />

        <MaterialButton
          class="email"
          id="antEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('anthonymarin718@gmail.com');
          }}
        />
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card" margin="auto">
      <img src={eric} alt="Eric" style="width:100%" />
      <div class="container">
        <h2>Eric Lemay</h2>
        <p class="title">Software Engineer</p>
        <MaterialButton
          class="github"
          id="ericGH"
          icon={githubIcon}
          text="Github"
          onClickFunction={() => {
            window.open('github.com/anthonymarinated');
          }}
        />

        <MaterialButton
          class="linkedin"
          id="ericLI"
          icon={linkedInIcon}
          text="LinkedIn"
          onClickFunction={() => {
            window.open('https://www.linkedin.com/in/eric-lemay-379659231/');
          }}
        />

        <MaterialButton
          class="email"
          id="ericEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('ericrogerlemay@gmail.com');
          }}
        />
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card">
      <img src={kristen} alt="Kristen" style="width:100%" />
      <div class="container">
        <h2>Kristen Althoff</h2>
        <p class="title">Software Engineer</p>
        <MaterialButton
          class="github"
          id="kristenGH"
          icon={githubIcon}
          text="Github"
          onClickFunction={() => {
            window.open('https://github.com/KristenWAlthoff');
          }}
        />

        <MaterialButton
          class="linkedin"
          id="kristenLI"
          text="LinkedIn"
          icon={linkedInIcon}
          onClickFunction={() => {
            window.open(
              'https://www.linkedin.com/in/kristen-althoff-3a4765b9/'
            );
          }}
        />

        <MaterialButton
          class="email"
          id="kristenEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('kristenwalthoff@gmail.com');
          }}
        />
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card">
      <img src={leo} alt="Leonoor" style="width:100%" />
      <div class="container">
        <h2>Leonoor Rinke de Wit</h2>
        <p class="title">Software Engineer</p>
        <MaterialButton
          class="github"
          id="leoGH"
          text="Github"
          icon={githubIcon}
          onClickFunction={() => {
            window.open('https://github.com/lrinkedewit');
          }}
        />

        <MaterialButton
          class="linkedin"
          id="leoLI"
          text="LinkedIn"
          icon={linkedInIcon}
          onClickFunction={() => {
            window.open('https://www.linkedin.com/in/leonoorrinkedewit/');
          }}
        />

        <MaterialButton
          class="email"
          id="leoEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('lrinkedewit@gmail.com');
          }}
        />
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card">
      <div class="container">
        <img src={stew} alt="Stewart" style="width:100%" />
        <h2>Stewart Elmore</h2>
        <p class="title">Software Engineer</p>
        <MaterialButton
          class="github"
          id="stewGH"
          icon={githubIcon}
          text="Github"
          onClickFunction={() => {
            window.open('https://github.com/selmore7');
          }}
        />

        <MaterialButton
          class="linkedin"
          id="stewLI"
          text="LinkedIn"
          icon={linkedInIcon}
          onClickFunction={() => {
            window.open('https://www.linkedin.com/in/stewart-elmore/');
          }}
        />

        <MaterialButton
          class="email"
          id="stewEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('stewart.elmore@gmail.com');
          }}
        />
      </div>
    </div>
  </div>
</div>

<style global lang="scss">
  @use '@material/button/styles';

  h1 {
    padding-top: 40px;
    padding-bottom: 40px;
  }
  .column {
    float: left;
    width: auto;
    margin-bottom: 16px;
    padding: 0 8px;
  }

  /* Display the columns below each other instead of side by side on small screens */
  @media screen and (max-width: 650px) {
    .column {
      width: 100%;
      display: block;
    }
  }

  .row {
    margin: auto;
    width: max-content;
  }

  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    outline: 2px solid rgb(8, 165, 238);
    margin: auto;
    width: 300px;
    border-radius: 20px;
  }

  .container {
    padding: 0 16px;
  }

  .container::after,
  .row::after {
    content: '';
    clear: both;
    display: table;
  }

  .title {
    color: rgb(90, 167, 218);
  }

  .button {
    border: none;
    outline: 0;
    display: inline-block;
    padding: 8px;
    text-align: center;
    cursor: pointer;
    width: 100%;
  }

  .button1 {
    background-color: black;
    color: ohite;
  }

  .button2 {
    background-color: blue;
  }

  .button:hover {
    background-color: blue;
  }
</style>
