<template>
<div class="row">
    <Rectangle
      v-for="(color, index) in colors" 
      :key="index" 
      :color='color'
    >
    </Rectangle>
</div>
</template>



<script>
import Rectangle from './Rectangle.vue'

export default {
  name: 'Rectangles',

  components: {
    Rectangle
  },

  props: {
    colors: Array
  },
  methods: {
  }
}
</script>



<style scoped>
</style>