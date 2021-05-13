<template>
	<v-container justify="center">
		<v-col class="col-8 offset-2" justify="center" align="center">
			<v-text-field
				v-model="portion_number"
				label="Nombre de personnes"
				type="number"
			></v-text-field>
			<v-text-field
				v-model="total_price"
				label="Prix total (€)"
				type="number"
			></v-text-field>
			<div v-for="index in parseInt(portion_number)" :key="index">
				<OrderCard @update-orders="updateOrders"/>
			</div>
			<v-btn>Commander</v-btn>
		</v-col>
	</v-container>
</template>

<script>
import OrderCard from '../components/Order_card'

export default {
	name: "Order",
	components: {
		OrderCard
	},
	data() {
		return {
			portion_number: 1,
			total_price: 15,
			orders: []
		};
	},
	methods: {
		updateOrders(order) {
			this.orders.push(order);
			console.log(this.orders);
		},
		order() {
			// API Commande UberEats
		}
	}
};
</script>

<style></style>
