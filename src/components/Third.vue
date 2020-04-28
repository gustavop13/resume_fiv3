<template>
  <section id='projects'>
    <div id='textContainer'>
      <div id='content'>
        <div id='cont'>
          <h2>My Projects</h2>
          <div id='desc'>
            I put a lot of thought into my work. I like to set my self
            apart by creating original projects that are interdisciplinary
            in nature.
          </div>
        </div>
      </div>
    </div>
    <div id='projectContainer'>
      <div id='projectWrapper'>
        <div id='cent'>
          <Proj class='proj'/>
          <Proj class='proj'/>
          <Proj class='proj'/>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

import Proj from './Proj.vue';

export default {
  name: 'Third',
  props: {
    msg: String
  },
  components: {
    Proj
  }
}
</script>

<style scoped>

#projects {
  width: 100%;
  height: 100%;
  margin: 0;
}

#textContainer {
  margin: 0;
  text-align: center;
  width: 50%;
  height: 100%;
  display: inline-block;
  overflow: hidden;
}

#projectContainer {
  width: 50%;
  height: 100%;
  margin: 0;
  text-align: center;
  display: inline-block;
  overflow: hidden;
}

#content {
  width: 80%;
  height: 100%;
  margin: auto;
  text-align: center;
  display: flex;
  align-items: center;
}

#cont {
  margin: auto;
}

h2 {
  width: 6em;
  margin: auto;
  margin-bottom: 1em;
  font-family: 'Montserrat', sans-serif;
  font-size: 40pt;
  font-weight: bold;
}

#desc {
  font-family: 'Montserrat', sans-serif;
  font-size: 16pt;
  width: 15em;
  margin: auto;
}

#projectWrapper {
  width: 100%;
  height: 100%;
  margin: 0;
  display: flex;
  align-items: center;
}

#cent {
  width: 80%;
  height: 70%;
  margin: auto;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.proj {
  width: 12em;
  height: 12em;
  border-radius: 8%;
  margin: 0;
  background-color: #f6006a;
}

</style>
