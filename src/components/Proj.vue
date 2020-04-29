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
          <a :href='link' target="_blank" class='codeLink'>View</a>
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
    startLink: String
  },
  data: function() {
    return {
      title: this.startTitle,
      desc: this.startDesc,
      source: require('../assets/' + this.iconName + '.svg'),
      link: this.startLink
    }
  },
  mounted: function() {
    let boxes = document.getElementsByClassName('iconBox');
    let colors = ['#f6006a', '#c100cd', '#00f197', '#f9f200', '#00e5fe'];
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
    width: 5em;
    display: block;
    margin: auto;
    margin-top: 0.5em;
    border-radius: 1.5em;
    text-align: center;
    font-size: 16pt;
    font-weight: bold;
    color: white;
    background-color: black;
    border: 3px solid white;
    cursor: pointer;
    text-decoration: none;
  }

  .textBox:hover {
    opacity: 0.9;
  }

  .codeLink:hover {
    background-color: white;
    color: black;
  }

</style>
