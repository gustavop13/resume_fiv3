<template>
  <section id="contact">
    <div id='header'>
      <h2>Find Out More</h2>
    </div>
    <div class='column'>
      <h3>
        Send Me an Email
      </h3>
      gustavop@email.arizona.edu
    </div>
    <div class='column'>
      <h3>
        Check Out My Github and LinkedIn
      </h3>
      gustavop@email.arizona.edu
    </div>
  </section>
</template>

<script>

//import gsap from 'gsap';

export default {
  name: 'Second',
  props: {
    msg: String,
  },
  components: {
  },
}

</script>

<style scoped>

  #contact {
    height: 100%;
    overflow: hidden;
    display: block;
    margin: 0;
    font-family: 'Montserrat', sans-serif;
  }

  #header {
    width: 100%;
    height: 30%;
    display: flex;
    align-items: center;
    text-align: center;
  }

  h2 {
    margin: auto;
    font-size: 40pt;
    font-weight: bold;
  }

  h3 {
    height: 4em;
    width: 10em;
    margin: auto;
    font-size: 28pt;
    font-weight: bold;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 3px solid #00f197;
    border-radius: 3px;
  }

  .column {
    width: 50%;
    height: 70%;
    margin: 0;
    overflow: hidden;
    display: inline-block;
    text-align: center;
  }

</style>
