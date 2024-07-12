<script setup>
import { defineEmits } from 'vue'

const emit = defineEmits(['set-component'])

const setComponent = (component) => {
  emit('set-component', component)
}
</script>

<template>
  <div>
    <button @click="setComponent('library')">Library</button>
    <button @click="setComponent('test')">Test</button>
    <button @click="setComponent('add')">Add New World</button>
  </div>
</template>

<style scoped>
body {
  display: flex;
}
button {
  color: white;
  background-color: #333;
  padding: 10px;
  margin: 5px;
  border: none;
  border-radius: 5px;
}
</style>