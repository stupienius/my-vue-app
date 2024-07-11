<script setup>
import { ref, onMounted } from 'vue';

const vocabularyList = ref([]);

const loadFromLocalStorage = () => {
    const savedList = localStorage.getItem('vocabularyList');
    if (savedList) {
        vocabularyList.value = JSON.parse(savedList);
    }
};

onMounted(() => {
    loadFromLocalStorage();
});
</script>

<template>
    <div>
        <h2>Vocabulary List</h2>
        <ul v-if="vocabularyList.length > 0">
            <li v-for="(entry, index) in vocabularyList" :key="index">
                <strong>{{ entry.word }}</strong>
                <span v-if="entry.chinese"> - {{ entry.chinese }}</span>
                <p v-if="entry.examples">Example: {{ entry.examples }}</p>
            </li>
        </ul>
        <p v-else>No vocabulary words saved yet.</p>
    </div>
</template>

<style scoped>
ul {
    list-style-type: none;
    padding: 0;
}

li {
    margin-bottom: 10px;
}
</style>