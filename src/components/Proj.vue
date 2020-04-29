<template>
  <div>
    <div class='iconBox'>
      <img class='icon' :src='source'/>
    </div>
  </div>
</template>

<script>

//import gsap from 'gsap';

export default {
  name: 'Proj',
  props: {
    msg: String,
    iconName: String
  },
  data: function() {
    return {
      source: require('../assets/' + this.iconName + '.svg'),
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

</style>
