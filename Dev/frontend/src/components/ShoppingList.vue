<template>
	<b-container fluid id = "showing">
		<b-row> 
			<b-col md="12" sm="12">
				<div id = "shopping-list"> 
					<h1> {{ header.toLocaleUpperCase() }} </h1>
					<ul> 
						<li v-for="item in items" v-bind:key="item	"> 
							{{ item }} 
						</li>
					</ul>
				</div>
			</b-col>
		</b-row>
	</b-container>
</template>

<script>
export default {
name: "ShoppingList",
	components: '',
	computed: '',
	data: function() {
		return {
			header: 'Shopping List App',
			items: [
				'10 Tomatos',
				'2 Salts',
				'1 Suggar',
				'3L Wather',
				'25 Cups'
			]
		}
	},
	methods: {
	},
	created() {
	}
}
</script>

<style>
#shopping-list {
	background-color: white;
	box-shadow: 2px 2px 3px 3px rgba(0, 0, 0, 0.2);
	padding: 20px;
	margin: 50px;
}

</style>