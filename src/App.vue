<script setup>
import Selection from './components/menu.vue'
import Banner from './components/banner.vue'
import Add from './components/add.vue'
import Library from './components/library.vue'
</script>

<template>
	<body>
		<header>
			<Banner/>
		</header>
		<main>
			<Selection/>
			<Add/>
			<Library/>
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
