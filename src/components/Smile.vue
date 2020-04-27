<template>
  <div>
    <svg v-on:click='anim()' id="redSmile" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 277.05 252.99"><path d="M280,126.62c0,187.21-260,187.21-260,0v.14c0-10.25,260-10.25,260,0ZM42.32,19.93,15.1,67.08A11.78,11.78,0,0,0,25.3,84.76H79.75A11.79,11.79,0,0,0,90,67.08L62.73,19.93A11.79,11.79,0,0,0,42.32,19.93Zm199,0L214.1,67.08a11.78,11.78,0,0,0,10.2,17.68h54.45A11.79,11.79,0,0,0,289,67.08L261.73,19.93A11.79,11.79,0,0,0,241.32,19.93Z" transform="translate(-13.5 -14.04)"/></svg>
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
      rotation: -30,
    }, {
      rotation: 30,
      duration: 3,
      repeat: -1,
      yoyo: true,
      ease: 'none'}
    );
    let parent = document.getElementById('smileCont');
    for(let i = 0; i < 7; i++) {
      let smileClone = document.getElementById('redSmile').cloneNode(true);
      smileClone.setAttribute('class', 'smile');
      smileClone.style.zIndex = -i-1;
      smileClone.style.width = '25%';
      smileClone.style.opacity = 0;
      parent.appendChild(smileClone);
    }
  },
  methods: {
    anim: function() {
      gsap.fromTo('.smile', {
        fill: function() {return gsap.utils.random(['#f6006a', '#00e5fe', '#f9f200', '#c100cd', '#00f197'])},
        x: 0,
        y: 0
      }, {
        x: function() {return gsap.utils.random(-150, 150)},
        y: function() {return gsap.utils.random(-150, 150)},
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
    width: 80%;
    height: 80%;
    margin: auto;
    cursor: pointer;
  }

  #redSmile {
    fill: #f9f200;
  }

  #redSmile:hover {
    fill: #00f197;
  }

  .smile {
    position: absolute;
    left: 25%;
    margin-right: -100px;
  }

</style>
