<template>
  <div id="app">
    <mouse></mouse>

    <div class="left">
        <h1>{{ msg_1 }}</h1>
        <p>{{ msg_2 }}</p>
        <a trigger>{{ msg_3 }}</a>  
    </div>
              
    <div class="right">
        <h1>{{ msg_1 }}</h1>
        <p>{{ msg_2 }}</p>
        <a trigger>{{ msg_3 }}</a>  
    </div> 

  </div>
</template>

<script>
import { TweenMax } from 'gsap';
import mouse from './components/mouse.vue';

export default {
  name: 'app',
  components:{
      mouse, 
    },
  data () {
    return {
      msg_1: 'Hello',
      msg_2: 'Check out this link:',
      msg_3: 'Hover me',
    }
  },
}
</script>

<style>
  body {
    top: 0;
    left: 0;
    margin: 0;
    padding: 0;
  }

  @import './assets/css/mouse.css';
</style>
