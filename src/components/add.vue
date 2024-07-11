<script setup>
import { ref, onMounted } from 'vue';

const vocabulary = ref('');
const chinese = ref('');
const exampleSentences = ref('');
const vocabularyList = ref([]);

const isAlphabetic = (str) => /^[a-zA-Z]+$/.test(str);

const submitVocabulary = () => {
	const trimmedVocabulary = vocabulary.value.trim();
	if (trimmedVocabulary && isAlphabetic(trimmedVocabulary)) {
		const entry = {
			word: trimmedVocabulary,
			chinese: chinese.value,
			examples: exampleSentences.value
		};

		vocabularyList.value.push(entry);
		saveToLocalStorage();

		vocabulary.value = '';
		chinese.value = '';
		exampleSentences.value = '';

		console.log('Vocabulary saved:', entry);
	} else if (!trimmedVocabulary) {
		alert('Please enter a vocabulary word.');
	} else {
		alert('The vocabulary word should consist only of alphabetic characters.');
	}
};

const saveToLocalStorage = () => {
	localStorage.setItem('vocabularyList', JSON.stringify(vocabularyList.value));
};

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
		<label for="w">Vocabulary</label>
		<input id="w" v-model="vocabulary" type="text" placeholder="necessary" required>

		<label for="ch">Chinese</label>
		<input id="ch" v-model="chinese" type="text" placeholder="Ignorable">

		<label for="eg">Example Sentences</label>
		<textarea id="eg" v-model="exampleSentences" placeholder="Ignorable" cols="30" rows="8"></textarea>

		<button id="sub" @click="submitVocabulary">Submit</button>
	</div>
</template>



<style scoped>
	div{
		display: flex;
		flex-direction: column;
		padding: 20px;
		background-color: gray;
	}
</style>