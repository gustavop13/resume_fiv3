<template>
  <section id="contact">
    <div id='header'>
      <h2>Find Out More</h2>
    </div>
    <div class='cForm'>
      <form action="/sendMesssage" method="GET">
        <label for="name">Name</label>
        <input type="text" id="name" name="name">
        <label for="email">Email Address</label>
        <input type="email" id="email" name="email">
        <label for="mes">Message</label>
        <textarea type="text" id="mes" name="message"></textarea>
        <input type="submit" value="Submit" id='send'>
      </form>
    </div>
    <div id='links'>
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
    </div>
    <ConcentricH/>
    <ConcentricS/>
  </section>
</template>

<script>

//import gsap from 'gsap';
import ConcentricH from './ConcentricH.vue';
import ConcentricS from './ConcentricS.vue';
//import Twinkle from './Twinkle.vue';

export default {
  name: 'Contact',
  props: {
    msg: String,
  },
  components: {
    ConcentricH,
    ConcentricS
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
    height: 15%;
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
    width: 100%;
    height: 6em;
    margin-top: 1em;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: white;
  }

  .iconLink {
    width: fit-content;
    text-align: center;
    margin: 2em 3em;
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

  .cForm {
    width: 100%;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  form {
    width: 70vh;
    margin: auto;
    text-align: left;
    display: flex;
    flex-direction: column;
  }

  label {
    width: 80%;
    margin: auto;
    font-size: 18pt;
    margin-top: 0.6em;
    font-weight: bold;
  }

  input, textarea {
    width: 80%;
    margin: auto;
    height: 3em;
    font-size: 12pt;
    padding-left: 8px;
    margin-top: 0.1em;
    font-family: 'Montserrat', sans-serif;
    border: 2px solid black;
  }

  input:focus {
    border-color: black black #00e5fe black;
    border-bottom-width: 4px;
  }

  input:hover {
    cursor: text;
  }

  #mes {
    height: 6em;
    padding-top: 10px;
  }

  #mes:focus {
    border-color: black black #00e5fe black;
    border-bottom-width: 4px;
  }

  #send {
    width: 83%;
    height: 2em;
    margin-top: 1em;
    cursor: pointer;
    text-align: center;
    color: white;
    background-color: #f6006a;
    border: none;
    font-size: 18pt;
  }

  #send:hover {
    background-color: #30384b;
  }

</style>
