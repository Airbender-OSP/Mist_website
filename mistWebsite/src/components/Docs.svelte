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
      <p id="docs1" on:click={(e) => navToggle(e)}>Tut Sect 1</p>
    </div>
    <div>
      <p id="docs2" on:click={(e) => navToggle(e)}>Tut Sect 2</p>
    </div>
    <div>
      <p id="docs3" on:click={(e) => navToggle(e)}>Tut Sect 3</p>
    </div>
    <div>
      <p id="docs4" on:click={(e) => navToggle(e)}>Tut Sect 4</p>
    </div>
    <div>
      <p id="docs5" on:click={(e) => navToggle(e)}>Tut Sect 5</p>
    </div>
    <div>
      <p id="docs6" on:click={(e) => navToggle(e)}>Tut Sect 6</p>
    </div>
  </section>
  <section id="documentation">
    <h1>DOCUMENTATION</h1>
    <div class="docsSec">
      <h3 id="navdocs1">Tut Sect 1</h3>
      <p>Stuff about tut sect 1....</p>
    </div>
    <div class="docsSec">
      <h3 id="navdocs2">Tut Sect 2</h3>
      <p>Stuff about tut sect 2....</p>
    </div>
    <div class="docsSec">
      <h3 id="navdocs3">Tut Sect 3</h3>
      <p>Stuff about tut sect 3....</p>
    </div>
    <div class="docsSec">
      <h3 id="navdocs4">Tut Sect 4</h3>
      <p>Stuff about tut sect 4....</p>
    </div>
    <div class="docsSec">
      <h3 id="navdocs5">Tut Sect 5</h3>
      <p>Stuff about tut sect 5....</p>
    </div>
    <div class="docsSec">
      <h3 id="navdocs6">Tut Sect 6</h3>
      <p>Stuff about tut sect 6....</p>
    </div>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
    <p>Yes</p>
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
  }
  .docsSec {
    margin-top: 5em;
    margin-left: 10em;
    text-align: left;
  }
</style>
