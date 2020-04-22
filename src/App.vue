<template>
  <div id="app">
    <First/>
  </div>
</template>

<script>
import First from './components/First.vue'

export default {
  name: 'App',
  components: {
    First
  }
}
</script>

//f6006a red
//00e5fe cyan
//f9f200 yellow
//c100cd purple
//00f197 green
<style>

body, html {
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100%;
}

body {
  display: grid;
  grid-template-columns: auto;
}

#app {
  height: 100%;
  width: 100%;
}
</style>
