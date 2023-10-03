<template>
  <div class="header">
    <button @click="drowRect">Rect</button>
  </div>
</template>

<script>
export default {
  emits: ['drow-rect'],
  methods: {
    drowRect() {
      console.log('Select drowRect')
      this.$emit('drow-rect')
    }
  }
}
</script>

<style scoped>
.header {
  height: 64px;
  padding: 8px 16px;
  box-shadow: 0 1px 8px 0 #f2f2f2;
}
</style>