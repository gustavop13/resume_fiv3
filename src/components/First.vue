<template>
  <div id="Top">
    Hi! I'm Gustavo Placencia.
    I'm a full-stack web developer.
    <StripeBg/>
  </div>
</template>

<script>

import StripeBg from './StripeBg.vue'
export default {
  name: 'First',
  props: {
    msg: String
  },
  components: {
    StripeBg
  }
}
</script>

<style scoped>

#Top {
  font-family: 'Montserrat', sans-serif;
  font-size: 32pt;
  font-weight: bold;
  display: block;
  width: 624px;
}
</style>
