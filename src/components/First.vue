<template>
  <section id="home">
    <Nav/>
    <StripeBg id='graphic1'/>
  </section>
</template>

<script>
import Nav from './Nav.vue'
import StripeBg from './StripeBg.vue'

export default {
  name: 'First',
  props: {
    msg: String
  },
  components: {
    Nav,
    StripeBg
  }
}
</script>

<style scoped>

#home {
  height: 100%;
}

#graphic1 {
  position: absolute;
  height: 350px;
  width: 100%;
  overflow: hidden;
}

</style>
