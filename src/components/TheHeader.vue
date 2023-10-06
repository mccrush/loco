<template>
  <div class="header">
    <BtnDraw @click="drawRect(50, 50, 50, 50)" title="Rect 50 50" />
    <BtnDraw @click="drawRect(150, 150, 50, 50)" title="Rect 150 150" />
    <BtnDraw @click="drawCurve" title="Line" />
    <BtnDraw @click="drawClear" title="Clear" />
  </div>
</template>

<script>
import BtnDraw from './BtnDraw.vue'

export default {
  components: { BtnDraw },
  emits: ['draw-rect', 'draw-curve', 'draw-clear'],
  methods: {
    drawRect(x, y, w, h) {
      console.log('Select drawRect')
      this.$emit('draw-rect', { x, y, w, h })
    },
    drawCurve() {
      console.log('drawCurve()')
      const arrayFigurs = JSON.parse(localStorage.getItem('arrayFigurs'))
      console.log('drawCurve() arrayFigurs = ', arrayFigurs)
      const x1 = arrayFigurs[0].x + 50
      const y1 = arrayFigurs[0].y + 25
      const x2 = arrayFigurs[1].x
      const y2 = arrayFigurs[1].y + 25

      // Но можно строить более плавные линии, если использовать разность Х
      const cp1x = x2
      const cp1y = y1
      const cp2x = x1
      const cp2y = y2

      this.$emit('draw-curve', { cp1x, cp1y, cp2x, cp2y, x1, y1, x2, y2 })
    },
    drawClear() {
      this.$emit('draw-clear')
    }
  }
}
</script>

<style scoped>
.header {
  height: 64px;
  padding: 16px 16px;
  box-shadow: 0 1px 8px 0 #f2f2f2;
}
</style>