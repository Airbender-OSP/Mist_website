<script>
  /* import assets from './assets'; */
  import MaterialButton from './MaterialButton.svelte';
  // import sass from 'node-sass';

  let anthony = '/images/Anthony.png';
  let eric = '/images/Eric.png';
  let kristen = '/images/Kristen.png';
  let leo = '/images/Leo.png';
  let stew = '/images/Stew.png';
  let linkedInIcon = '/images/linkedIn.png';
  let gmailIcon = '/images/gmail.png';
  let githubIcon = '/assets/github120.png';
</script>

<div>
  <h1>Meet The Team</h1>
</div>

<div class="row">
  <div class="column">
    <div class="card">
      <img
        src={anthony}
        alt="Anthony"
        style="width:80%; margin: auto; margin-top: 20px; height: 200px; width: 200px"
      />
      <div class="container">
        <h2 style="font-size: 20px">
          Anthony Marin<br /><span style="font-size: 16px; color: #9d9d9d"
            >Software Engineer</span
          >
        </h2>
        <!-- <p class="title">Software Engineer</p> -->
        <MaterialButton
          class="github"
          id="antGH"
          icon={githubIcon}
          text="Github"
          onClickFunction={() => {
            window.open('https://github.com/anthonymarinated');
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

        <!-- <MaterialButton
          class="email"
          id="antEmail"
          text="anthonymarin718@gmail.com"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('anthonymarin718@gmail.com');
          }}
        /> -->
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card" margin="auto">
      <img
        src={eric}
        alt="Eric"
        style="width:80%; margin: auto; margin-top: 20px; height: 200px; width: 200px"
      />
      <div class="container">
        <h2 style="font-size: 20px">
          Eric Lemay<br /><span style="font-size: 16px; color: #9d9d9d"
            >Software Engineer</span
          >
        </h2>
        <!-- <p class="title">Software Engineer</p> -->
        <MaterialButton
          class="github"
          id="ericGH"
          icon={githubIcon}
          text="Github"
          onClickFunction={() => {
            window.open('https://github.com/StygianLiege');
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

        <!-- <MaterialButton
          class="email"
          id="ericEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('ericrogerlemay@gmail.com');
          }}
        /> -->
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card">
      <img
        src={kristen}
        alt="Kristen"
        style="width:80%; margin: auto; margin-top: 20px; height: 200px; width: 200px"
      />
      <div class="container">
        <h2 style="font-size: 20px">
          Kristen Althoff<br /><span style="font-size: 16px; color: #9d9d9d"
            >Software Engineer</span
          >
        </h2>
        <!-- <p class="title">Software Engineer</p> -->
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

        <!-- <MaterialButton
          class="email"
          id="kristenEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('kristenwalthoff@gmail.com');
          }}
        /> -->
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card">
      <img
        src={leo}
        alt="Leonoor"
        style="width:80%; margin: auto; margin-top: 20px; height: 200px; width: 200px"
      />
      <div class="container">
        <h2 style="font-size: 20px">
          Leonoor Rinke de Wit<br /><span
            style="font-size: 16px; color: #9d9d9d">Software Engineer</span
          >
        </h2>
        <!-- <p class="title">Software Engineer</p> -->
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

        <!-- <MaterialButton
          class="email"
          id="leoEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('lrinkedewit@gmail.com');
          }}
        /> -->
      </div>
    </div>
  </div>

  <div class="column">
    <div class="card">
      <div class="container">
        <img
          src={stew}
          alt="Stewart"
          style="width:80%; margin: auto; margin-top: 20px; height: 200px; width: 200px"
        />
        <h2 style="font-size: 20px">
          Stewart Elmore<br /><span style="font-size: 16px; color: #9d9d9d"
            >Software Engineer</span
          >
        </h2>
        <!-- <p class="title">Software Engineer</p> -->
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

        <!-- <MaterialButton
          class="email"
          id="stewEmail"
          text="Email"
          icon={gmailIcon}
          onClickFunction={() => {
            window.open('stewart.elmore@gmail.com');
          }}
        /> -->
      </div>
    </div>
  </div>
</div>

<style global lang="scss">
  @use '@material/button/styles';
  @import '../../public/global.scss';
  // #f9f9f9
  // #e9e9e9

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
  // @media screen and (max-width: 650px) {
  //   .column {
  //     width: 100%;
  //     display: flex;
  //   }
  // }

  .row {
    display: flex;
    flex-direction: row;
    align-content: center;
    justify-content: center;
    margin: auto;
    width: auto;
    flex-wrap: wrap;
  }

  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    outline: 2px solid #9d9d9d;
    margin: auto;
    width: 250px;
    border-radius: 20px;
    background-color: #e9e9e9;
  }

  .container {
    padding: 0 16px;
    display: flex;
    flex-direction: column;
  }

  .container::after,
  .row::after {
    content: '';
    clear: both;
    display: table;
  }

  .title {
    color: #6194bc;
  }

  .github {
    color: black;
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
</style>
