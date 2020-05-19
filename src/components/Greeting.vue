<template>
  <div id='container'>
    <div id='greeting'>
      <div id='content'>
        Hi! I'm Gustavo.
        I'm a full-stack web developer.
        <a href='mailto:gustavop@email.arizona.edu' id='emailButton'>Hire Me</a>
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

a {
  width: 8em;
  height: 2em;
  margin-top: 1em;
  display: flex;
  align-items: center;
  font-size: 18pt;
  font-weight: bold;
  color: black;
  background-color: #00f197;
  text-decoration: none;
  border-radius: 2em;
  text-align: left;
  justify-content: center;
}

a:hover {
  background-color: black;
  color: #00f197;
}

</style>
