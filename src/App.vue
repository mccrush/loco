<template>
  <div>
    <TheHeader @drow-rect="drowRect" />
    <BlockCanvas ref="canvas" />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import BlockCanvas from './components/BlockCanvas.vue'

export default {
  components: { TheHeader, BlockCanvas },
  methods: {
    drowRect() {
      this.$refs.canvas.drowRect()
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>