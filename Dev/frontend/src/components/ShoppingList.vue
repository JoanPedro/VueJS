<template>
	<b-container fluid id = "showing">
		<b-row> 
			<b-col md="12" sm="12">
				<div class = "shopping-list"> 
					<b-row>
						<b-col md="9" sm="9"> 
							<h1> {{ header.toLocaleUpperCase() }} </h1>
						</b-col>
						<b-col md="3" sm="3"> 
							<b-button variant="primary" v-if="state === 'default'" @click="changeState('edit')"> Add item </b-button>
							<b-button variant="danger" v-else @click="changeState('default')"> Cancel </b-button>
							<b-button variant="primary" @click="items = []" class = "ml-2"> Clear </b-button>
						</b-col>
					</b-row>
					<b-row>
						<b-col md="9" sm="9"
						v-if="state === 'edit'"
						class="add-item-form">
							<b-input v-model="newItem" 
							type="text" 
							placeholder ="Insert an new item"
							class ="mb-2 mt-2"
							@keyup.enter="addItem()">  
							</b-input>
						</b-col>
						<b-col md="3" sm="3"
						v-if="state === 'edit'"	> 
							<b-button variant="success"
							class ="mb-2 mt-2"
							@click="addItem()"> 
								Save Item 
							</b-button>
						</b-col>
					</b-row>
					<ul> 
						<li v-for="item in items" v-bind:key="item	"> 
							{{ item }} 
						</li>
					</ul>
					<span v-if="items.length === '0'"> Você comprou todos os seus itens. </span>
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
			state: 'default',
			header: 'Shopping List App',
			searching: 'Filtering by Name',
			newItem: '',
			items: [
				// '10 Tomatos',
				// '2 Salts',
				// '1 Suggar',
				// '3L Wather',
				// '25 Cups'
			],
			query: ''
		}
	},
	methods: {
		addItem: function() {
			if(this.newItem != '') this.items.push(this.newItem)
			this.newItem = ''
		},
		filterListByName: function() {
			return this.items.filter()
		},
		changeState: function(newState) {
			this.state = newState
		}
	},
	created() {
	}
}
</script>

<style>
.shopping-list {
	background-color: white;
	box-shadow: 2px 2px 3px 3px rgba(0, 0, 0, 0.2);
	padding: 20px;
	margin: 50px;
}

</style>
