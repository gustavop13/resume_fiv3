<template>
  <section id="contact">
    <div id='header'>
      <h2>Find Out More</h2>
    </div>
    <div id='links'>
      <a href='mailto:gustavop@email.arizona.edu' id='emailButton'>Email Me</a>
      <div class='iconLink'>
        <a href='https://www.linkedin.com/in/gustavo-placencia-carranza/' target='_blank'>
          <img src='../assets/LI.png'/>
        </a>
      </div>
      <div class='iconLink'>
        <a href='https://github.com/gustavop13' target='_blank'>
          <img src='../assets/gHub.png'/>
        </a>
      </div>
      <Twinkle/>
    </div>
    <ConcentricH/>
    <ConcentricS/>
  </section>
</template>

<script>

//import gsap from 'gsap';
import ConcentricH from './ConcentricH.vue';
import ConcentricS from './ConcentricS.vue';
import Twinkle from './Twinkle.vue';

export default {
  name: 'Contact',
  props: {
    msg: String,
  },
  components: {
    ConcentricH,
    ConcentricS,
    Twinkle
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
    position: relative;
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

  #links {
    width: fit-content;
    margin: auto;
    position: relative;
    background-color: white;
  }

  .iconLink {
    width: 100%;
    text-align: center;
    margin-top: 3em;
  }

  img {
    width: 5em;
    margin: auto;
  }

  #emailButton {
    width: 8em;
    height: 2em;
    display: flex;
    align-items: center;
    margin: auto;
    font-size: 18pt;
    font-weight: bold;
    color: black;
    background-color: #00f197;
    text-decoration: none;
    border-radius: 2em;
    text-align: center;
    justify-content: center;
  }

  #emailButton:hover {
    background-color: black;
    color: #00f197;
  }

</style>
