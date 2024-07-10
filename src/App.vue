<script setup>
	import HelloWorld from './components/HelloWorld.vue'
	import selection from './components/menu.vue'
	import banner from './components/banner.vue'
</script>

<template>
	<body>		
		<header>
			<banner/>
			<selection/>
		</header>
		<main>
		</main>
	</body>
</template>

<style scoped>
	body{
		display: flex;
		flex-direction: row;
	}
	header{
		display: flex;
		flex-direction: column;
	}
	.menu{
		height: auto;
	}
	main{
		background-color: gray;
	}
</style>
