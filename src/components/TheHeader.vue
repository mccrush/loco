<template>
  <div class="header">
    <BtnDraw @click="drawRect(50, 50, 50, 50)" title="Rect 50 50" />
    <BtnDraw @click="drawRect(150, 150, 50, 50)" title="Rect 150 150" />
    <BtnDraw @click="drawCurve(125, 175, 150, 175)" title="Line" />
  </div>
</template>

<script>
import BtnDraw from './BtnDraw.vue'

export default {
  components: { BtnDraw },
  emits: ['draw-rect', 'draw-curve'],
  methods: {
    drawRect(x, y, w, h) {
      console.log('Select drawRect')
      this.$emit('draw-rect', { x, y, w, h })
    },
    drawCurve(cpx, cpy, x, y) {
      console.log('Select drawCurve')
      this.$emit('draw-curve', { cpx, cpy, x, y })
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