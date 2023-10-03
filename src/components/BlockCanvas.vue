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
        let ctx = canvas.getContext('2d')
        //ctx.transform(1, 0, 0, -1, 0, canvas.height)
        return ctx
      }
    },
    drawRect({ x, y, w, h }) {
      console.log('drawRect in canvas')
      let ctx = this.drawInit()
      ctx.strokeRect(x, y, w, h)
    },
    drawCurve({ cp1x, cp1y, cp2x, cp2y, x, y }) {
      console.log('drawRect in canvas')
      let ctx = this.drawInit()
      ctx.beginPath()
      ctx.moveTo(100, 75)
      ctx.bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)

      //ctx.quadraticCurveTo(cpx, cpy - 100, x - 25, y - 50)

      //ctx.moveTo(125, 125)
      //ctx.quadraticCurveTo(cpx, cpy, x, y)
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