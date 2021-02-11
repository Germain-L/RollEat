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
				<v-card class="py-5 px-5 my-3" elevation="0" outlined>
					<v-text-field
						label="Nom de la personne"
						type="text"
					></v-text-field>
					<v-select :items="diets" label="Régime alimentaire"></v-select>
					<v-text-field
						label="Aliments non désiré / Allergies / Intolerance"
						type="text"
					></v-text-field>
				</v-card>
			</div>
			<v-btn>Commander</v-btn>
		</v-col>
	</v-container>
</template>

<script>
export default {
	name: "Order",
	data() {
		return {
      diets: ['De tout', 'Végan', 'Végétarien', 'Pescétarien'],
			portion_number: 1,
			total_price: 15,
			orders: {}
		};
	}
};
</script>

<style></style>
