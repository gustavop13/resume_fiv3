<template>
  <section id='projects'>
    <div id='title'>
      <h2>My Projects</h2>
    </div>
    <div id='projectContainer'>
      <div id='projectWrapper'>
        <div id='cent'>
          <Proj class='proj' iconName='note' startLink='http://gustavop.com/noise' startTitle="Orange Noise" startDesc="Song visualizer collection" v-bind:liveSite="true"/>
          <Proj class='proj' iconName='three' startLink='http://gustavop.com/3' startTitle="resume_three" startDesc="Old resume site showcasing three.js" v-bind:liveSite="true"/>
          <Proj class='proj' iconName='tv' startLink='https://movienight.space' startTitle="Movie Night" startDesc="A helpful tool to simplify the process of choosing a movie" v-bind:liveSite="true"/>
          <Proj class='proj' iconName='ghost' startLink='https://github.com/gustavop13/Haunter' startTitle="Haunter's Call" startDesc="Digital narrative with call and text functionality made in Processing"/>
          <Proj class='proj' iconName='dumbbell' startLink='https://github.com/gustavop13/Ardufit' startTitle="Ardufit" startDesc="Resistance-centered fitness tracking web-service"/>
          <Proj class='proj' iconName='die' startLink='https://github.com/gustavop13/movie_night' startTitle="HRNG" startDesc="Hardware Random Number Generator with web API"/>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

import Proj from './Proj.vue';

export default {
  name: 'Projects',
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
  height: fit-content;
  min-height: 100%;
  display: block;
  margin: 0;
}

#title {
  width: 100%;
  height: 20%;
  display: flex;
  align-items: center;
  justify-content: center;
}

#projectContainer {
  width: 100%;
  height: 100%;
  margin: 0;
  text-align: center;
  display: inline-block;
  overflow: hidden;
}

h2 {
  font-family: 'Montserrat', sans-serif;
  font-size: 40pt;
  font-weight: bold;
}

#desc {
  font-family: 'Montserrat', sans-serif;
  font-size: 16pt;
  width: 15em;
  margin: auto;
  margin-top: 3em;
  margin-bottom: 3em;
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
  width: 14em;
  height: 14em;
  margin: 1em 0;
  background-color: white;
}

</style>
