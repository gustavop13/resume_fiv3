<template>
  <div>
    <svg v-on:click='anim()' id="redHeart" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 241.47 225.87"><title>Untitled-2</title><path d="M225.16,122.66,161.29,193c-.93,1-35.33,38.2-36.26,37.18L29.16,123.68C-37,50.2,59.29-39.36,125.92,31.5a2.19,2.19,0,0,0,3.25,0C197.48-41.32,293,47.27,225.16,122.66Z" transform="translate(-6.95 -4.36)"/></svg>
  </div>
</template>

<script>

import gsap from 'gsap';

export default {
  name: 'Heart',
  props: {
    msg: String,
  },
  mounted: function() {
    gsap.fromTo('#redHeart', {
      rotation: -30,
    }, {
      rotation: 30,
      duration: 3,
      repeat: -1,
      yoyo: true,
      ease: 'none'}
    );
    let parent = document.getElementById('heartCont');
    for(let i = 0; i < 7; i++) {
      let heartClone = document.getElementById('redHeart').cloneNode(true);
      heartClone.setAttribute('class', 'heart');
      heartClone.style.zIndex = -i-1;
      heartClone.style.width = '25%';
      heartClone.style.opacity = 0;
      parent.appendChild(heartClone);
    }
  },
  methods: {
    anim: function() {
      gsap.fromTo('.heart', {
        fill: function() {return gsap.utils.random(['#f6006a', '#00e5fe', '#f9f200', '#c100cd', '#00f197'])},
        x: 0,
        y: 0
      }, {
        x: function() {return gsap.utils.random(-150, 150)},
        y: function() {return gsap.utils.random(-150, 150)},
        duration: 0.4,
      });
      gsap.fromTo('.heart', {
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
    cursor: pointer;
    margin: auto;
  }

  #redHeart {fill: #f6006a}

  #redHeart:hover {
    fill: #c100cd;
  }

  .heart {
    position: absolute;
    left: 25%;
    margin-right: -100px;
  }

</style>
