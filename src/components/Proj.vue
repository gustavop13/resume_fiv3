<template>
  <div>
    <div id='smileBox'>
      <svg v-on:click='anim()' id="redSmile" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 241.47 225.87"><path d="M238.6,108C238.6,271.11,12,271.11,12,108v.11c0-8.92,226.57-8.92,226.57,0ZM30.17,17.26,9.07,53.81a11.78,11.78,0,0,0,10.2,17.67h42.2A11.78,11.78,0,0,0,71.68,53.81L50.58,17.26A11.79,11.79,0,0,0,30.17,17.26Zm173.42,0-21.1,36.55a11.78,11.78,0,0,0,10.2,17.67h42.2a11.78,11.78,0,0,0,10.2-17.67L224,17.26A11.79,11.79,0,0,0,203.59,17.26Z" transform="translate(-7.47 -11.37)"/></svg>
    </div>
  </div>
</template>

<script>

//import gsap from 'gsap';

export default {
  name: 'Proj',
  props: {
    msg: String,
  },
}

</script>

<style scoped>

  #smileBox {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
  }

  #redSmile {
    fill: #f9f200;
    width: 80%;
    height: 80%;
    margin: auto;
  }

</style>
