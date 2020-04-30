<template>
  <div id='container'>
    <svg xmlns="http://www.w3.org/2000/svg" id='main' class='int' viewBox="0 0 58.88 56"><g id="inner"><polygon points="15.17 35.59 3.73 22.6 20.62 18.82 29.44 3.93 38.26 18.82 55.15 22.6 43.71 35.59 45.33 52.82 29.44 45.95 13.55 52.82 15.17 35.59" style="fill:#c100cd"/><path d="M130,99.85l6.66,11.25.88,1.48,1.69.38L152,115.82l-8.63,9.8-1.14,1.3.16,1.72,1.22,13-12-5.18-1.59-.69-1.58.69-12,5.18,1.23-13,.16-1.72-1.14-1.3-8.64-9.8L120.76,113l1.69-.38.88-1.48L130,99.85M130,92l-10.1,17.06-19.34,4.33,13.1,14.88L111.79,148,130,140.14l18.2,7.86-1.86-19.73,13.1-14.88-19.34-4.33L130,92Z" style="fill:#c100cd" transform="translate(-100.54 -92)"/></g></svg>
    </div>
</template>

<script>

import gsap from 'gsap';

export default {
  name: 'Twinkle',
  props: {
    msg: String,
  },
  mounted: function() {
    let parent = document.getElementById('links');
    let xPositions = [-350, -200, -150, 420, 250, 300, 400];
    let yPositions = [100, -50, 200, 200, 100, 300, 0];
    for(let i = 0; i < 7; i++) {
      let twinkleClone = document.getElementById('main').cloneNode(true);
      twinkleClone.style.left = xPositions[i];
      twinkleClone.style.top = yPositions[i];
      parent.appendChild(twinkleClone);
    }
    gsap.fromTo('.int', {
      scale: 0.4,
    }, {
      scale: 0.6,
      duration: 1,
      repeat: -1,
      yoyo: true,
      ease: 'steps(1)'
    });
  },
}

</script>

<style scoped>

#container {
  width: fit-content;
  height: fit-content;
  text-align: center;
  position: absolute;
  top: 0;
}

svg {
  width: 5em;
  stroke: #c100cd;
  overflow: visible;
  position: absolute;
  z-index: -1;
}

</style>
