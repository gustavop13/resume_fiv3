<template>
  <div id='nav'>
    <h3 class='s' id='aboutButton' v-on:click='scrollTo'>About</h3>
    <h3 class='s' id='projectsButton' v-on:click='scrollTo'>Projects</h3>
    <h3 class='s' id='contactButton' v-on:click='scrollTo'>Contact</h3>
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
      let elId = "about";
      if(event.target.id === 'aboutButton') {
        elId = "about";
      } else if(event.target.id === 'projectsButton') {
        elId = "projects";
      } else if(event.target.id === 'contactButton') {
        elId = "contact";
      }
      gsap.to(document.body, {
        scrollTop: document.getElementById(elId).getBoundingClientRect().top,
        duration: 1,
        ease: 'power1.out'
      });
      gsap.to(document.documentElement, {
        scrollTop: document.getElementById(elId).getBoundingClientRect().top,
        duration: 1,
        ease: 'power1.out'
      });
    }
  }
}
</script>

<style scoped>

#nav {
  width: 100%;
  height: 10em;
  margin: 0;
  padding: 0;
  font-family: 'Montserrat', sans-serif;
  font-size: 14pt;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
}

h3 {
  width: 5em;
  text-align: center;
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
