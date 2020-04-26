<template>
  <div id='container'>
    <div id='nav'>
      <h3 class='s' id='aboutButton' v-on:click='scrollTo'>About</h3>
      <h3 class='s' id='projectsButton' v-on:click='scrollTo'>Projects</h3>
      <h3 class='s' id='contactButton' v-on:click='scrollTo'>Contact</h3>
    </div>
  </div>
</template>

<script>
import gsap from 'gsap';
export default {
  name: 'Nav',
  props: {
    msg: String
  },
  mounted: function() {
    gsap.from(".s", {
      opacity: 0,
      duration: 2,
      stagger: 0.4,
      delay: 3
    });
  },
  methods: {
    scrollTo: function(event) {
      let mult = 1;
      if(event.target.id === 'aboutButton') {
        mult = 1;
      } else if(event.target.id === 'projectsButton') {
        mult = 2;
      } else if(event.target.id === 'contactButton') {
        mult = 3;
      }
      gsap.to(document.body, {
        scrollTop: mult * window.innerHeight,
        duration: 1,
        ease: 'power1.out'
      });
      gsap.to(document.documentElement, {
        scrollTop: mult * window.innerHeight,
        duration: 1,
        ease: 'power1.out'
      });
    }
  }
}
</script>

<style scoped>

#container {
  width: 100%;
  height: 33%;
  font-family: 'Montserrat', sans-serif;
  font-size: 14pt;
  font-weight: bold;
  text-align: center;
  display: flex;
  align-items: center;
  overflow: auto;
}

#nav {
  width: fit-content;
  margin: auto;
  margin-bottom: 80px;
  display: flex;
  align-items: center;
}

h3 {
  margin: -20px;
  width: 200px;
  cursor: pointer;
  transition: color 1s;
}

h3:hover {
  transition: color 0.3s;
}

#aboutButton:hover {
  color: #f6006a;
}
#projectsButton:hover {
  color: #c100cd;
}
#contactButton:hover {
  color: #00f197;
}

</style>
