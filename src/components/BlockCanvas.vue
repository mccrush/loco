<template>
  <canvas width="600" height="420" id="canvas"> Drow </canvas>
</template>

<script>
export default {
  methods: {
    drawInit() {
      console.log('init Draw')
      let canvas = document.getElementById('canvas')
      if (canvas.getContext) {
        return canvas.getContext('2d')
      }
    },
    drawRect({ x, y, w, h }) {
      console.log('drawRect in canvas')
      let ctx = this.drawInit()
      // ctx.fillRect(25, 25, 100, 100)
      // ctx.clearRect(45, 45, 60, 60)
      ctx.strokeRect(x, y, w, h)
    },
    drawCurve({ cpx, cpy, x, y }) {
      console.log('drawRect in canvas')
      let ctx = this.drawInit()
      ctx.beginPath()
      ctx.moveTo(100, 75)
      ctx.quadraticCurveTo(cpx, cpy - 100, x - 25, y - 50)

      ctx.moveTo(125, 125)
      ctx.quadraticCurveTo(cpx, cpy, x, y)
      ctx.stroke()
    }
  }
}
</script>

<style scoped>
#canvas {
  border: 1px solid #a3a3a3;
}
</style>