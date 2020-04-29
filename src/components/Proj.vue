<template>
  <div>
    <div class='iconBox'>
      <img id='icon' :src='source'/>
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
    boxes.forEach((ele) => {
      ele.style.backgroundColor = 'red';
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

  #icon {
    width: 80%;
    height: 80%;
    margin: auto;
  }

</style>
