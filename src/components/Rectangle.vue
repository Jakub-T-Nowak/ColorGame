<template>
  <div class="col-lg-4 h-100px">
    <transition name="fade">
      <div
      class="h-100px"
      :style="style"
      v-on:click="show = !show"
      v-if="show"
      >
        <p >{{color}}</p>
      </div>
    </transition>
  </div>
</template>


<script>
export default {
  name: 'Rectangle',

  props: {
    color:Object
  },

  data() {return {
    show: true
  }},

  computed: {
    style () {
      const {r, g, b} = this.color;

      if (r + g + b < 300) {
        return 'background-color: rgb(' + r + ', ' + g + ', ' + b + ');' + ' color: white;';
      }
      return 'background-color: rgb(' + r + ', ' + g + ', ' + b + ');';
    }
  },
  
  methods: {
  }
}
</script>


<style scoped>
div {
  width: 100%;
}
p {
  margin: 0px;
}
.col-lg-4 {
  padding: 0px;
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>