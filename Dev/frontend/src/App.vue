<template>
	<div id="app">
		<ShoppingList />
	</div>
</template>

<script>
import ShoppingList from './components/ShoppingList'
export default {
	name: "App",
	components: {ShoppingList},
	computed: '',
	data: function() {
		return {
		}
	},
	methods: {
	},
	created() {
	}
}
</script>

<style>
body { 
	background: turquoise;
}

</style>