<template>
  <canvas width="600" height="420" class="canvas"> Drow </canvas>
</template>

<script>
export default {
  methods: {
    drowInit() {},
    drowRect() {
      console.log('drowRect in canvas')
    }
  }
}
</script>

<style scoped>
.canvas {
  border: 1px solid #a3a3a3;
}
</style>