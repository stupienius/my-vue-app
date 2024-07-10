<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Menu from './components/menu.vue'
</script>

<template>
  <header>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <Menu class="menu" />
  </header>
</template>

<style scoped>
header{
  display: flex;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.menu{
  height: auto;
}
</style>
