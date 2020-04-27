<template>
  <section id="about" v-on:scroll='handleScroll'>
    <div id='container'>
      <div id='desc'>
        <div id='content'>
          I'm a graduate of the University of Arizona,
          where I majored in Information Science and
          minored in Astronomy. I tend to work on projects
          that require a variety of skills.
        </div>
      </div>
      <div id='icons'>
        <Star id='starCont'/>
        <Heart id='heartCont'/>
        <Smile id='smileCont'/>
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
        gsap.fromTo('#starCont', {
          x: '200px',
        }, {
          x: '0px',
          opacity: 1,
          duration: 2,
        });
        gsap.fromTo('#heartCont', {
          x: '200px',
        }, {
          x: '0px',
          opacity: 1,
          duration: 2,
        });
        gsap.fromTo('#smileCont', {
          x: '200px',
        }, {
          x: '0px',
          opacity: 1,
          duration: 2,
        });
        gsap.fromTo('#desc', {
          x: '-200px',
          opacity: 0
        }, {
          x: 0,
          opacity: 1,
          duration: 2,
        });
        this.displayed = true;
      }
    }
  }
}

</script>

<style scoped>

  #about {
    height: 100%;
    display: flex;
    align-items: center;
    overflow: hidden;
  }

  #container{
    width: 100%;
    height: 40%;
    display: flex;
    align-items: center;
  }

  #desc {
    width: 50%;
    margin: 0;
    text-align: center;
    opacity: 0;
  }

  #content {
    font-family: 'Montserrat', sans-serif;
    font-size: 20pt;
    font-weight: bold;
    width: 15em;
    margin: auto;
  }

  #icons {
    width: 50%;
    height: 100%;
    display: flex;
    align-items: center;
    margin-right: 5em;
  }

  #heartCont {
    width: 33%;
    height: 50%;
    text-align: center;
    opacity: 0
  }

  #starCont {
    width: 33%;
    height: 50%;
    text-align: center;
    opacity: 0
  }

  #smileCont {
    width: 33%;
    height: 50%;
    text-align: center;
    opacity: 0
  }

</style>
