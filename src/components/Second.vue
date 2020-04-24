<template>
  <section id="layout1">
  </section>
</template>

<script>
export default {
  name: 'Second',
  props: {
    msg: String
  },
  components: {
    
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
  height: 300px;
  width: 100%;
}

</style>
