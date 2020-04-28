<template>
  <div id='stripeBg'>
    <Greeting id='henlo'/>
    <div class='white'>
      <div class='stripe' id='red'>
      </div>
    </div>
    <div class='white'>
      <div class='stripe' id='cyan'>
      </div>
    </div>
    <div class='white'>
      <div class='stripe' id='yellow'>
      </div>
    </div>
    <div class='white'>
      <div class='stripe' id='purple'>
      </div>
    </div>
    <div class='white'>
      <div class='stripe' id='green'>
      </div>
    </div>
  </div>
</template>

<script>
  import gsap from 'gsap';
  import Greeting from './Greeting.vue'

  export default {
    name: 'StripeBg',
    components: {
      Greeting
    },
    mounted: function() {
      gsap.from(".stripe", {
        right: window.innerWidth,
        duration: 5,
        delay: 1,
        stagger: 0.2,
        ease: 'elastic'
      });
      gsap.from("#henlo", {
        opacity: 0,
        duration: 2,
        delay: 2
      });
    }
  }
</script>

<style>
  #stripeBg {
    display: flex;
    align-items: center;
  }
  #henlo {
    position: absolute;
    width: 50%;
    margin: auto;
    z-index: -1;
    padding: 70px 0px;
  }
  .white {
    height: 20%;
    width: 100%;
    margin: 0;
  }

  .stripe {
    height: 20%;
    position: absolute;
    right: 0;
    width: 500px;
  }

  .white:hover #red {
    width: 35%;
    transition: width 1s;
     -webkit-transition: width 1s;
  }

  .white:hover #cyan {
    width: 40%;
    transition: width 1s;
     -webkit-transition: width 1s;
  }

  .white:hover #yellow {
    width: 45%;
    transition: width 1s;
     -webkit-transition: width 1s;
  }

  .white:hover #purple {
    width: 30%;
    transition: width 1s;
     -webkit-transition: width 1s;
  }

  .white:hover #green {
    width: 45%;
    transition: width 1s;
     -webkit-transition: width 1s;
  }

  #red {
    background-color: #f6006a;
    width: 25%;
    transition: width 1s;
    -webkit-transition: width 1s;
  }
  #cyan {
    background-color: #00e5fe;
    width: 30%;
    transition: width 1s;
    -webkit-transition: width 1s;
  }
  #yellow {
    background-color: #f9f200;
    width: 35%;
    transition: width 1s;
    -webkit-transition: width 1s;
  }
  #purple {
    background-color: #c100cd;
    width: 40%;
    transition: width 1s;
    -webkit-transition: width 1s;
  }
  #green {
    background-color: #00f197;
    width: 50%;
    transition: width 1s;
    -webkit-transition: width 1s;
  }
</style>
