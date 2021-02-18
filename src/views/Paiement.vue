<template>
	<v-container justify="center">
		<v-col class="cols-6">
			<v-card class="mx-auto" max-width="344" outlined>
				<v-list-item three-line>
					<v-list-item-content>
						<div class="overline mb-4">Total</div>
						<v-list-item-title class="headline mb-1">
							Moyen de payement
						</v-list-item-title>
						<v-text-field
							label="Numéro de carte"
							type="int"
							v-model="num_card"
						></v-text-field>
						<v-text-field
							label="Expire à fin"
							type="int"
							v-model="validity"
						></v-text-field>
						<v-text-field
							label="Code sécurité"
							type="int"
							v-model="security"
						></v-text-field>
					</v-list-item-content>
				</v-list-item>

				<v-card-actions>
					<v-btn outlined rounded text> Visa </v-btn>
				</v-card-actions>
				<v-card-actions>
					<v-btn outlined rounded text> PayPal </v-btn>
				</v-card-actions>
			</v-card>
		</v-col>

		<v-col class="cols-6">
			<v-card class="mx-auto" max-width="344" outlined>
				<v-list-item three-line>
					<v-list-item-content>
						<div class="overline mb-4">Total</div>
						<v-list-item-title class="headline mb-1">
							Sous-total
						</v-list-item-title>
						<v-list-item-subtitle
							>Frais de port
						</v-list-item-subtitle>
						<v-list-item-subtitle
							>Frais de service
						</v-list-item-subtitle>
					</v-list-item-content>

					<!-- // Pourquoi pas mettre la map de la livraison à la place --}} -->
					<v-list-item-avatar
						tile
						size="80"
						color="grey"
					></v-list-item-avatar>
				</v-list-item>

				<v-card-actions>
					<v-btn outlined rounded text> Button </v-btn>
				</v-card-actions>
			</v-card>
		</v-col>
	</v-container>
</template>

<script>
export default {};
</script>

<style scoped></style>
