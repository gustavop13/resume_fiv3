<template>
  <section id="about">
    <div id='container'>
      <div id='int' v-on:click='anim'>
        <svg class='star' id="cyanStar" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 373.11 354.85"><title>Untitled-1</title><polygon points="186.56 0 250.55 108.08 373.11 135.54 290.1 229.8 301.85 354.85 186.56 305.02 71.26 354.85 83.02 229.8 0 135.54 122.56 108.08 186.56 0"/></svg>
        <svg class='star' id="yellowStar" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 373.11 354.85"><title>Untitled-1</title><polygon points="186.56 0 250.55 108.08 373.11 135.54 290.1 229.8 301.85 354.85 186.56 305.02 71.26 354.85 83.02 229.8 0 135.54 122.56 108.08 186.56 0"/></svg>
        <svg class='star' id="purpleStar" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 373.11 354.85"><title>Untitled-1</title><polygon points="186.56 0 250.55 108.08 373.11 135.54 290.1 229.8 301.85 354.85 186.56 305.02 71.26 354.85 83.02 229.8 0 135.54 122.56 108.08 186.56 0"/></svg>
        <svg class='star' id="greenStar" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 373.11 354.85"><title>Untitled-1</title><polygon points="186.56 0 250.55 108.08 373.11 135.54 290.1 229.8 301.85 354.85 186.56 305.02 71.26 354.85 83.02 229.8 0 135.54 122.56 108.08 186.56 0"/></svg>
        <svg id="redStar" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 373.11 354.85"><title>Untitled-1</title><polygon points="186.56 0 250.55 108.08 373.11 135.54 290.1 229.8 301.85 354.85 186.56 305.02 71.26 354.85 83.02 229.8 0 135.54 122.56 108.08 186.56 0"/></svg>
      </div>
      <div id='desc'>
        I'm a graduate of the University of Arizona,
        where I majored in Information Science and
        minored in Astronomy. I tend to work on projects
        that require a variety of skills.
      </div>
    </div>
  </section>
</template>

<script>

import gsap from 'gsap';

export default {
  name: 'Second',
  props: {
    msg: String
  },
  methods: {
    anim: function() {
      gsap.fromTo('.star', {
        x: 0,
        y: 0
      }, {
        x: function() {return gsap.utils.random(-250, 250)},
        y: function() {return gsap.utils.random(-250, 250)},
        duration: 0.4,
        stagger: 0.05
      });
      gsap.fromTo('.star', {
        opacity: 1
      }, {
        opacity: 0,
        duration: 0.4,
        ease: 'power2.in'
      });
    }
  }
}

</script>

<style scoped>

  #about {
    height: 100%;
    display: flex;
    align-items: center;
  }

  #container{
    width: 80%;
  }

  #desc {
    width: 20em;
    font-family: 'Montserrat', sans-serif;
    font-size: 20pt;
    font-weight: bold;
    margin: auto;
    text-align: center;
  }

  svg {
    width: 200px;
    position: absolute;
    left: 500px;
    cursor: pointer;
  }

  .star {
    opacity: 1;
  }

  #redStar {fill: red}
  #cyanStar {fill: cyan}
  #yellowStar {fill: yellow}
  #purpleStar {fill: purple}
  #greenStar {fill: green}


</style>
