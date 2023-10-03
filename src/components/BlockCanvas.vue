<template>
  <canvas width="600" height="420" id="canvas"> Drow </canvas>
</template>

<script>
export default {
  data() {
    return {
      ctx: null
    }
  },
  methods: {
    drawInit() {
      console.log('init Draw')
      let canvas = document.getElementById('canvas')
      if (canvas.getContext) {
        this.ctx = canvas.getContext('2d')
        //ctx.transform(1, 0, 0, -1, 0, canvas.height)
        //return ctx
      }
    },
    drawRect({ x, y, w, h }) {
      console.log('drawRect in canvas')
      if (!this.ctx) {
        this.drawInit()
      }
      this.ctx.strokeRect(x, y, w, h)
    },
    drawCurve({ cp1x, cp1y, cp2x, cp2y, x, y }) {
      console.log('drawCurve in canvas')
      if (!this.ctx) {
        this.drawInit()
      }
      this.ctx.beginPath()
      this.ctx.moveTo(100, 75)
      this.ctx.bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
      this.ctx.stroke()
    }
  }
}
</script>

<style scoped>
#canvas {
  border: 1px solid #a3a3a3;
}
</style>