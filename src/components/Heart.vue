<template>
  <div>
    <div id='heartBox'>
      <svg v-on:click='anim()' id="redHeart" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 241.47 225.87"><path d="M225.16,124.66,161.29,195c-.93,1-35.33,38.2-36.26,37.18L29.16,125.68C-37,52.2,59.29-37.36,125.92,33.5a2.19,2.19,0,0,0,3.25,0C197.48-39.32,293,49.27,225.16,124.66Z" transform="translate(-6.95 -6.36)"/></svg>
    </div>
  </div>
</template>

<script>

import gsap from 'gsap';

export default {
  name: 'heart',
  props: {
    msg: String,
  },
  mounted: function() {
    gsap.fromTo('#redHeart', {
      rotation: -20,
    }, {
      rotation: 20,
      duration: 3,
      repeat: -1,
      yoyo: true,
      ease: 'none'}
    );
    let parent = document.getElementById('heartBox');
    for(let i = 0; i < 7; i++) {
      let heartClone = document.getElementById('redHeart').cloneNode(true);
      heartClone.setAttribute('class', 'heart');
      heartClone.setAttribute('id', 'idk');
      heartClone.style.zIndex = -i-1;
      heartClone.style.width = '3em';
      heartClone.style.opacity = 0;
      heartClone.style.position = 'absolute';
      heartClone.style.left = parent.getBoundingClientRect().left + parent.clientWidth/2;
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
        x: function() {return gsap.utils.random(-120, 120)},
        y: function() {return gsap.utils.random(-120, 120)},
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
    cursor: pointer;
  }

  #redHeart {
    fill: #f6006a;
  }

  #redHeart:hover {
    fill: #c100cd;
  }

</style>
