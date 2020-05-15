<template>
  <div id="app">
    <Landing/>
    <Projects/>
    <About/>
    <Contact/>
  </div>
</template>

<script>
import Landing from './components/Landing.vue'
import Projects from './components/Projects.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components: {
    Landing,
    Projects,
    About,
    Contact
  },
}
</script>
<style>

body, html {
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
}

body {
  position: relative;
}

#app {
  height: 100%;
  width: 100%;
}
</style>
