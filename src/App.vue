<template>
  <div id="app">
  <div class="container">
    <Navigation v-on:start="start" :color="colors[n]"/>
    <Rectangles v-bind:colors='colors'/>
  </div>
  </div>
</template>

<script>
import 'bootstrap'
import 'bootstrap/dist/css/bootstrap.min.css'
import Navigation from './components/Navigation.vue'
import Rectangles from './components/Rectangles.vue'

export default {
  name: 'App',
  components: {
    Navigation, Rectangles
  },
  data() {return {
    n: 1,
    colors: [
      {r:255, g:255, b:255},
      {r:255, g:255, b:255},
      {r:255, g:255,b:255}]
  }},
  methods: {
    start: function () {
        this.colors.forEach(color => {
          color.r = this.randomRGB()
          color.g = this.randomRGB()
          color.b = this.randomRGB()
        });
        
        this.n = this.getRandom(0,2)
    },
    
    getRandom(min, max) {
      min = Math.ceil(min);
      max = Math.floor(max);
      return Math.floor(Math.random() * (max - min + 1) + min);
    },

    randomRGB () {
       return this.getRandom(0, 255);
    }


  }
}
</script>

<style>
#app {
  text-align: center;
}

div {
  position: relative;
  display: block;
}

.h-100px {
  height: 50px;
}

@media (min-width: 768px){
  .container, .container-md, .container-sm {
    max-width: 700px;
  } 
  .h-100px {
  height: 100px;
}
}
</style>
