<template>
  <canvas width="600" height="420" id="canvas" @click="drawFromMouse($event)">
    Drow
  </canvas>
</template>

<script>
export default {
  data() {
    return {
      canvas: null,
      ctx: null,
      width: 50,
      height: 50,
      arrayFigurs: []
    }
  },
  methods: {
    drawInit() {
      console.log('init Draw')
      this.canvas = document.getElementById('canvas')
      if (this.canvas.getContext) {
        this.ctx = this.canvas.getContext('2d')
      }
    },
    drawRect({ x, y, w, h }) {
      console.log('drawRect in canvas')
      if (!this.ctx) {
        this.drawInit()
      }
      this.ctx.strokeRect(x, y, w, h)

      this.arrayFigurs.push({ x, y })
      localStorage.setItem('arrayFigurs', JSON.stringify(this.arrayFigurs))
      console.log('LS arrayFigurs = ', localStorage.getItem('arrayFigurs'))
    },
    drawCurve({ cp1x, cp1y, cp2x, cp2y, x1, y1, x2, y2 }) {
      console.log('drawCurve in canvas')
      if (!this.ctx) {
        this.drawInit()
      }
      this.ctx.beginPath()
      this.ctx.moveTo(x1, y1)
      this.ctx.bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x2, y2)
      this.ctx.stroke()
    },
    drawFromMouse(e) {
      const X = e.clientX
      const Y = e.clientY
      const startX = X - this.width / 2
      const starty = Y - this.height * 2
      this.drawRect({ x: startX, y: starty, w: this.width, h: this.height })
    },
    drawClear() {
      console.log('drawClear in canvas')
      if (!this.ctx) {
        this.drawInit()
      }
      this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height)
      this.arrayFigurs = []
      localStorage.setItem('arrayFigurs', JSON.stringify(this.arrayFigurs))
    }
  }
}
</script>

<style scoped>
#canvas {
  border: 1px solid #a3a3a3;
}
</style>