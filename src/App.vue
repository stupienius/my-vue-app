<script setup>
	import Selection from './components/menu.vue'
	import Banner from './components/banner.vue'
	import Add from './components/add.vue'
</script>

<template>
	<body>		
		<header>
			<Banner/>
		</header>
		<main>
			<Selection/>
			<Add />
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
		display: flex;
		flex-direction: column;
		background-color: gray;	
	}
</style>
