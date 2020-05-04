<template>
  <div id="app">
    <First/>
    <Second/>
    <Third/>
    <Fourth/>
  </div>
</template>

<script>
import First from './components/First.vue'
import Second from './components/Second.vue'
import Third from './components/Third.vue'
import Fourth from './components/Fourth.vue'

export default {
  name: 'App',
  components: {
    First,
    Second,
    Third,
    Fourth
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
