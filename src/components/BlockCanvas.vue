<template>
  <canvas width="600" height="420" class="canvas"> Drow </canvas>
</template>

<script>
export default {
  methods: {
    drowInit() {
      console.log('init Drow')
    },
    drowRect() {
      console.log('drowRect in canvas')
      this.drowInit()
    }
  }
}
</script>

<style scoped>
.canvas {
  border: 1px solid #a3a3a3;
}
</style>