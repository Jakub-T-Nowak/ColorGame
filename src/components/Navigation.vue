<template>
<div class="row h-100px">
  <div
    :style="style"
    class="col"
    @click='click'
  >    
    {{start}}
  </div>
</div>
</template>


<script>
export default {
  name: 'Navigation',

  data() {return {
    isActive: false,
    start: 'CLICK TO START'
  }},

  props: {
    color: Object
  },

  computed: {
    style () {
      const {r, g, b} = this.color;
      let bc = `background-color: rgb(${r},${g},${b});`
      return (r + g + b < 300) ? bc.conat(' color: white;') : bc
    }
  },

  methods: {
    click: function () {
      this.start = ''
      this.$emit('start')
    }
  }
}
</script>


<style scoped>
button {
  margin: 10px;
}
div {
  
  background-color: blue;
}
</style>
