<template>
  <div id='container'>
    <div id='greeting'>
      <div id='content'>
        Hi! I'm Gustavo.
        I'm a full-stack web developer.
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Greeting',
}
</script>

<style scoped>

#container {
  width: 50%;
  float: left;
  height: 300px;
}
#greeting {
  width: 100%;
  text-align: center;
}
#content {
  font-family: 'Montserrat', sans-serif;
  font-size: 32pt;
  font-weight: bold;
  width: 350px;
  margin: auto;
  text-align: left;
}

</style>
