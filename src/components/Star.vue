<template>
  <div>
    <div id='starBox'>
      <svg v-on:click='anim()' id="redStar" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 373.11 354.85"><polygon points="186.56 0 250.55 108.08 373.11 135.54 290.1 229.8 301.85 354.85 186.56 305.02 71.26 354.85 83.02 229.8 0 135.54 122.56 108.08 186.56 0"/></svg>
    </div>
  </div>
</template>

<script>

import gsap from 'gsap';

export default {
  name: 'Star',
  props: {
    msg: String,
  },
  mounted: function() {
    gsap.fromTo('#redStar', {
      rotation: -20,
    }, {
      rotation: 20,
      duration: 3,
      repeat: -1,
      yoyo: true,
      ease: 'none'}
    );
    let parent = document.getElementById('starBox');
    for(let i = 0; i < 7; i++) {
      let starClone = document.getElementById('redStar').cloneNode(true);
      starClone.setAttribute('class', 'star');
      starClone.setAttribute('id', 'idk');
      starClone.style.zIndex = -i-1;
      starClone.style.opacity = 0;
      starClone.style.width = '3em';
      starClone.style.position = 'absolute';
      starClone.style.left = 0;
      parent.appendChild(starClone);
    }
  },
  methods: {
    anim: function() {
      gsap.fromTo('.star', {
        fill: function() {return gsap.utils.random(['#f6006a', '#00e5fe', '#f9f200', '#c100cd', '#00f197'])},
        x: 0,
        y: 0
      }, {
        x: function() {return gsap.utils.random(-120, 120)},
        y: function() {return gsap.utils.random(-120, 120)},
        duration: 0.4,
      });
      gsap.fromTo('.star', {
        opacity: 1
      }, {
        opacity: 0,
        duration: 0.4,
        ease: 'power2.in'
      });
    },
  }
}

</script>

<style scoped>

  svg {
    cursor: pointer;
  }

  #starBox {
    position: relative;
  }

  #redStar {
    fill: #00e5fe;
  }

  #redStar:hover {
    fill: #00f197;
  }

</style>
