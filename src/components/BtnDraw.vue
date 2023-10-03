<template>
  <button>{{ title }}</button>
</template>

<script>
export default {
  props: { title: String }
}
</script>

<style scoped>
button {
  margin-right: 8px;
  padding: 4px;
  background: #f2f2f2;
  border: 1px solid #e7e7e7;
  border-radius: 4px;
  cursor: pointer;
}

button:hover,
button:active {
  background: #e7e7e7;
}
</style>