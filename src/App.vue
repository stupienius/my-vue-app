<script setup>
import { ref } from 'vue'
import Selection from './components/menu.vue'
import Banner from './components/banner.vue'
import Add from './components/add.vue'
import Library from './components/library.vue'
import Test from './components/test.vue'
import Xata from './components/xata.vue'

const activeComponent = ref('library')

const setActiveComponent = (component) => {
  activeComponent.value = component
}
</script>

<template>
  <body>
    <header>
      <Banner />
      <Xata />
    </header>
    <main>
      <Selection @set-component="setActiveComponent" />
      <Add v-if="activeComponent === 'add'" />
      <Library v-if="activeComponent === 'library'" />
      <Test v-if="activeComponent === 'test'"/>
    </main>
  </body>
</template>

<style scoped>
body {
  display: flex;
  flex-direction: row;
}
header {
  display: flex;
  flex-direction: column;
}
.menu {
  height: auto;
}
main {
  display: flex;
  flex-direction: column;
}
</style>