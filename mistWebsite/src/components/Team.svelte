<script>
  /* import assets from './assets'; */

</script>

<div>
  <h1>Meet The Team!</h1>
</div>

<div class="row"> 

  <div class="column">
        <div class="card">
          <img src="" alt="Anthony" style="width:100%">
          <div class="container">
            <h2>Anthony Marin</h2>
            <p class="title">Software Engineer</p>
              <p>
                <button class="button1">
                  <a href="github.com/anthonymarinated">Github</a>
                </button>
              </p>
              <p>
                <button class="button2">
                  <a href="https://www.linkedin.com/in/anthmari/">LinkedIn</a>
                </button>
              </p>
              <a href="anthonymarin718@gmail.com">Email</a>          
          </div>
        </div>
      </div>
    
      <div class="column">
        <div class="card">
          <img src="" alt="Eric" style="width:100%">
          <div class="container">
            <h2>Eric Lemay</h2>
            <p class="title">Software Engineer</p>
              <p>
                <button class="button1">
                  <a href="github.com/StygianLiege">Github</a>
                </button>
              </p>
              <p>
                <button class="button2">
                  <a href="https://www.linkedin.com/in/eric-lemay-379659231/">LinkedIn</a>
                </button>
              </p>
              <a href="https://www.linkedin.com/in/eric-lemay-379659231/" alt="alt">Email</a>          
          </div>
        </div>
      </div>



      <div class="column">
        <div class="card">
          <img src="" alt="Kristen" style="width:100%">
          <div class="container">
            <h2>Kristen Althoff</h2>
            <p class="title">Software Engineer</p>
              <p>
                <button class="button1">
                  <a href="https://github.com/KristenWAlthoff">Github</a>
                </button>
              </p>
              <p>
                <button class="button2">
                  <a href="https://www.linkedin.com/in/kristen-althoff-3a4765b9/">LinkedIn</a>
                </button>
              </p>
              <a href="https://www.linkedin.com/in/kristen-althoff-3a4765b9/">Email</a>          
          </div>
        </div>
      </div>

        
      <div class="column">
        <div class="card">
          <img src="" alt="Leonoor" style="width:100%">
          <div class="container">
            <h2>Leonoor Rinke de Wit</h2>
            <p class="title">Software Engineer</p>
              <p>
                <button class="button1">
                  <a href="https://github.com/lrinkedewit">Github</a>
                </button>
              </p>
              <p>
                <button class="button2">
                  <a href="https://www.linkedin.com/in/leonoorrinkedewit/">LinkedIn</a>
                </button>
              </p>
              <a href="lrinkedewit@gmail.com">Email</a>          
          </div>
        </div>
      </div>


      <div class="column">
        <div class="card">
          <img src="" alt="Stewart" style="width:100%">
          <div class="container">
            <h2>Stewart Elmore</h2>
            <p class="title">Software Engineer</p>
              <p>
                <button class="button1">
                  <a href="https://github.com/selmore7">Github</a>
                </button>
              </p>
              <p>
                <button class="button2">
                  <a href="https://www.linkedin.com/in/stewart-elmore/">LinkedIn</a>
                </button>
              </p>
              <a href="stewart.elmore@gmail.com">Email</a>          
          </div>
        </div>
      </div>  


</div>

<style>
  div.row{
    margin: auto;
  } 

  h1{
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

  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
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
    color:ohite;
  }

  .button2 {
    background-color: blue;
  }
/* 
  .button:hover {
    background-color: blue;
  } */
</style>
