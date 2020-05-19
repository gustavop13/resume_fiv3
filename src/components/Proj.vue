<template>
  <div>
    <div class='iconBox'>
      <img class='icon' :src='source'/>
      <div class='textBox'>
        <div class='title'>
          {{title}}
        </div>
        <div class='text'>
          {{desc}}
          <a :href='link' target="_blank" class='codeLink' v-if="live">
            View Site
          </a>
          <a :href='link' target="_blank" class='codeLink' v-else>
            View Code
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

//import gsap from 'gsap';

export default {
  name: 'Proj',
  props: {
    msg: String,
    iconName: String,
    startTitle: String,
    startDesc: String,
    startLink: String,
    liveSite: Boolean
  },
  data: function() {
    return {
      title: this.startTitle,
      desc: this.startDesc,
      source: require('../assets/' + this.iconName + '.svg'),
      link: this.startLink,
      live: this.liveSite
    }
  },
  mounted: function() {
    let boxes = document.getElementsByClassName('iconBox');
    let colors = ['#00f197', '#c100cd', '#f9f200', '#f6006a', '#00e5fe', '#00f197'];
    boxes.forEach((ele, idx) => {
      ele.style.backgroundColor = colors[idx];
    });
  }
}

</script>

<style scoped>

  .iconBox {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
  }

  .icon {
    width: 70%;
    height: 70%;
    margin: auto;
  }

  .textBox {
    width: 14em;
    height: 14em;
    margin: 0;
    background-color: black;
    position: absolute;
    opacity: 0;
    transition: opacity 0.6s;
    -webkit-transition: opacity 0.6s;
  }

  .title {
    width: 100%;
    height: 30%;
    font-family: 'Montserrat', sans-serif;
    font-size: 20pt;
    font-weight: bold;
    color: white;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .text {
    width: 10em;
    margin: auto;
    font-family: 'Montserrat', sans-serif;
    font-size: 14pt;
    color: white;
    text-align: center;
  }

  .codeLink {
    width: 7em;
    height: 2em;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: auto;
    margin-top: 0.5em;
    border-radius: 1.5em;
    text-align: center;
    font-size: 12pt;
    font-weight: bold;
    color: white;
    background-color: black;
    border: 3px solid white;
    cursor: pointer;
    text-decoration: none;
  }

  .textBox:hover {
    opacity: 0.9;
    -webkit-transition: opaity 0.6s;
    transition: opacity 0.6s;
  }

  .codeLink:hover {
    background-color: white;
    color: black;
  }

</style>
