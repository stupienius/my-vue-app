<template>
    <div>
      <h1>Data from Xata</h1>
      <ul>
        <li v-for="item in items" :key="item.id">{{ item.name }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  import { XataClient } from '../xata';
  
  const items = ref([]);
  
  onMounted(async () => {
    const xata = new XataClient();
    const response = await xata.db['stu-database'].getAll();
    items.value = response.records;
  });
  </script>
  


  