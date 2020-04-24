<template>
  <section id="layout1">
    <StripeBg id='graphic1'/>
  </section>
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

#layout1 {
  height: 100%;
  display: flex;
  align-items: center;
}

#graphic1 {
  position: absolute;
  height: 350px;
  width: 100%;
}

</style>
