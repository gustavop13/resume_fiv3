<template>
  <div>
    <div id='smileBox'>
      <svg v-on:click='anim()' id="redSmile" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 241.47 225.87"><path d="M238.6,108C238.6,271.11,12,271.11,12,108v.11c0-8.92,226.57-8.92,226.57,0ZM30.17,17.26,9.07,53.81a11.78,11.78,0,0,0,10.2,17.67h42.2A11.78,11.78,0,0,0,71.68,53.81L50.58,17.26A11.79,11.79,0,0,0,30.17,17.26Zm173.42,0-21.1,36.55a11.78,11.78,0,0,0,10.2,17.67h42.2a11.78,11.78,0,0,0,10.2-17.67L224,17.26A11.79,11.79,0,0,0,203.59,17.26Z" transform="translate(-7.47 -11.37)"/></svg>
    </div>
  </div>
</template>

<script>

import gsap from 'gsap';

export default {
  name: 'Smile',
  props: {
    msg: String,
  },
  mounted: function() {
    gsap.fromTo('#redSmile', {
      rotation: -20,
    }, {
      rotation: 20,
      duration: 3,
      repeat: -1,
      yoyo: true,
      ease: 'none'}
    );
    let parent = document.getElementById('smileBox');
    for(let i = 0; i < 7; i++) {
      let SmileClone = document.getElementById('redSmile').cloneNode(true);
      SmileClone.setAttribute('class', 'smile');
      SmileClone.setAttribute('id', 'idk');
      SmileClone.style.zIndex = -i-1;
      SmileClone.style.opacity = 0;
      SmileClone.style.width = '3em';
      SmileClone.style.position = 'absolute';
      SmileClone.style.left = 0;
      parent.appendChild(SmileClone);
    }
  },
  methods: {
    anim: function() {
      gsap.fromTo('.smile', {
        fill: function() {return gsap.utils.random(['#f6006a', '#00e5fe', '#f9f200', '#c100cd', '#00f197'])},
        x: 0,
        y: 0
      }, {
        x: function() {return gsap.utils.random(-120, 120)},
        y: function() {return gsap.utils.random(-120, 120)},
        duration: 0.4,
      });
      gsap.fromTo('.smile', {
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

  #smileBox {
    position: relative;
  }

  #redSmile {
    fill: #f9f200;
  }

  #redSmile:hover {
    fill: #00f197;
  }

</style>
