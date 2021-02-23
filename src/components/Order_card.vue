<template>
	<v-card class="py-5 px-5 my-3" elevation="0" outlined>
		<v-text-field
			label="Nom de la personne"
			type="text"
			v-model="orderData.nameData"
		></v-text-field>
		<v-select
			:items="diets"
			label="Régime alimentaire"
			v-model="orderData.dietData"
		></v-select>
		<v-text-field
			label="Aliments non désiré / Allergies / Intolerance"
			type="text"
			v-model="orderData.foodBlackListData"
		></v-text-field>
		<v-btn @click="postOrders()">Ajouter</v-btn>
		<v-snackbar v-model="snackbar" timeout="3000">
			{{ this.snackbarText }}

			<template v-slot:action="{ attrs }">
				<v-btn
					color="blue"
					text
					v-bind="attrs"
					@click="snackbar = false"
				>
					Fermer
				</v-btn>
			</template>
		</v-snackbar>
	</v-card>
</template>

<script>
export default {
	name: "OrderCard",

	data() {
		return {
			diets: ["De tout", "Végan", "Végétarien", "Pescétarien"],
			orderData: {
				nameData: "",
				dietData: "",
				foodBlackListData: []
			},
			iconColour: "white",
			snackbar: false,
			snackbarText: ""
		};
	},
	methods: {
		postOrders() {
			if (this.orderData.nameData == "") {
				this.snackbarText = "Erreur: Ajouter des noms";
				this.snackbar = true;
			} else if (this.orderData.dietData == "") {
				this.snackbarText = "Erreur: Ajouter des régimes";
				this.snackbar = true;
			} else {
				this.$emit("update-orders", this.orderData);
			}
		}
	}
};
</script>
<style></style>
