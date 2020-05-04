<template>
  <section id="about" v-on:scroll='handleScroll'>
    <div id='header'>
      <h2>About Me =D</h2>
    </div>
    <div id='container'>
      <div class='column'>
        <div class='item'>
          <div id='content'>
            I'm a graduate of the University of Arizona,
            where I majored in Information Science and
            minored in Astronomy. I tend to work on projects
            that require a large variety of skills.
          </div>
          <Star id='starCont' class='icon'/>
        </div>
      </div>
      <div class='column'>
        <div class='item'>
          <div id='content'>
            I'm always trying to develop new skills. These days
            I mostly focus on web development and trying out
            different libraries and frameworks.
          </div>
          <Heart id='heartCont' class='icon'/>
        </div>
      </div>
      <div class='column'>
        <div class='item'>
          <div id='content'>
            I am as well rounded a person as you'll ever meet and
            I like to make that apparent through my projects. If
            you'd like to ask about any of them be sure to send me
            an e-mail. I'm always happy to talk about them.
          </div>
          <Smile id='smileCont' class='icon'/>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

import gsap from 'gsap';
import Star from './Star.vue';
import Heart from './Heart.vue';
import Smile from './Smile.vue';

export default {
  name: 'Second',
  props: {
    msg: String,
  },
  components: {
    Star,
    Heart,
    Smile
  },
  data() {
    return {
      displayed: false,
    }
  },
  created () {
    window.addEventListener('scroll', this.handleScroll);
    this.displayed = false;
  },
  methods: {
    handleScroll: function() {
      if(window.scrollY > window.innerHeight * 0.8 & !this.displayed) {
        gsap.to('.item', {
          opacity: 1,
          duration: 2,
          stagger: 0.5
        });
        this.displayed = true;
      }
    }
  }
}

</script>

<style scoped>

  #about {
    height: fit-content;
    min-height: 100%;
    display: block;
    margin: 0;
    padding-top: 3em;
  }

  #header {
    width: 100%;
    height: 40%;
    margin-top: 3em;
    margin-bottom: 3em;
    display: flex;
    align-items: center;
    text-align: center;
  }

  h2 {
    margin: auto;
    font-family: 'Montserrat', sans-serif;
    font-size: 40pt;
    font-weight: bold;
  }

  #container {
    width: 100%;
    min-height: 100%;
    margin: auto;
    text-align: center;
    display: flex;
    align-items: flex-start;
    flex-wrap: wrap;
    justify-content: space-around;
  }

  .column {
    width: 20em;
    height: 100%;
    margin: 2em;
    display: inline-block;
    overflow: visible;
  }

  .item {
    height: 80%;
    width: 100%;
    text-align: center;
    opacity: 0;
    overflow: visible;
  }

  #content {
    font-family: 'Montserrat', sans-serif;
    font-size: 16pt;
    width: 15em;
    margin: auto;
  }

  .icon {
    width: 33%;
    height: 30%;
    text-align: center;
    opacity: 1;
    margin: auto;
    margin-top: 3em;
    overflow: visible;
  }

</style>
