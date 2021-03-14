<template>
	<v-container justify="center">
		<h1 class="col-8 offset-2 pl-5">Mes commandes</h1>
		<v-col class="col-8 row offset-2" justify="center" align="center">
			<div v-for="index in history" :key="index" class="col-6">
				<v-card class=" pa-1">
					<v-row class="pa-5" justify="space-between">
						<h2>{{ index.name }}</h2>
						<h3>{{ index.price }}</h3>
					</v-row>
					<v-col class="text-left">
						<div v-for="order in index.orders" :key="order">
							{{ ` • ${order}` }}
						</div>
					</v-col>
				</v-card>
			</div>
		</v-col>
	</v-container>
</template>

<script>
export default {
	name: "History",
	//TODO Get data [history] from firebase
	data() {
		return {
			history: [
				{
					name: "SuAndShi",
					price: "32€",
					orders: [
						"Yakitori",
						"Beateau",
						"Menu McJapon",
						"Californian",
						"Theo"
					]
				},
				{
					name: "SuAndShi",
					price: "32€",
					orders: [
						"Yakitori",
						"Beateau",
						"Menu McJapon",
						"Californian",
						"Theo"
					]
				},
				{
					name: "SuAndShi",
					price: "32€",
					orders: [
						"Yakitori",
						"Beateau",
						"Menu McJapon",
						"Californian",
						"Theo"
					]
				},
				{
					name: "SuAndShi",
					price: "32€",
					orders: [
						"Yakitori",
						"Beateau",
						"Menu McJapon",
						"Californian",
						"Theo"
					]
				}
			]
		};
	}
};
</script>

<style></style>
