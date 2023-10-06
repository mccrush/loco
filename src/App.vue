<template>
  <div>
    <TheHeader @draw-rect="drawRect" @draw-curve="drawCurve" />
    <BlockCanvas ref="canvas" />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import BlockCanvas from './components/BlockCanvas.vue'

export default {
  components: { TheHeader, BlockCanvas },
  methods: {
    drawRect({ x, y, w, h }) {
      this.$refs.canvas.drawRect({ x, y, w, h })
    },
    drawCurve({ cp1x, cp1y, cp2x, cp2y, x1, y1, x2, y2 }) {
      this.$refs.canvas.drawCurve({ cp1x, cp1y, cp2x, cp2y, x1, y1, x2, y2 })
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