<script setup>
import { defineEmits, ref } from 'vue'

const emit = defineEmits(['set-component'])
const modul = ref(0)
console.log(modul === 0)
const setComponent = (component, index) => {
  emit('set-component', component)
  modul.value = index
}
</script>

<template>
  <div>
    <button @click="setComponent('library', 0)" :class="{ isSelect: modul === 0 }">Library</button>
    <button @click="setComponent('test', 1)" :class="{ isSelect: modul === 1 }">Test</button>
    <button @click="setComponent('add', 2)" :class="{ isSelect: modul === 2 }">Add New World</button>
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

.isSelect {
  background-color: yellow;
  color: black;
}
</style>