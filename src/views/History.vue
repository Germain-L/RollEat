<template>
	<div class="history">
		<v-container>
			<v-col cols="12">
				<h1 class="font-weight-light text-center">Vos dernières commandes</h1>
			</v-col>

			<v-row>
				<v-col cols="4" v-for="order in orders" :key="order.id">
					<v-card class="mx-auto my-12">
						<template slot="progress">
							<v-progress-linear color="deep-purple" height="10" indeterminate></v-progress-linear>
						</template>

						<v-img height="250" :src="order.img"></v-img>

						<v-card-title>{{ order.name }}</v-card-title>

						<v-card-text>
							<v-row align="center" class="mx-0">
								<v-rating :value="Math.random() * (5 - 3) + 3" color="amber" background-color="#eee" dense half-increments readonly size="14"></v-rating>

								<div class="grey--text ml-4">
									{{ order.rating }}
								</div>
							</v-row>

							<div class="my-4 subtitle-1">
								{{ order.price }} € • {{ order.people }} personnes
							</div>

							<div>
								{{ order.description }}
							</div>
						</v-card-text>

						<v-divider class="mx-4"></v-divider>

						<v-card-actions>
							<v-btn color="primary" text>
								Commander de nouveau
							</v-btn>
							<v-btn color="info" text>
								Voir la commande
							</v-btn>
							<br/>
							<v-btn text>
								👍
							</v-btn>
							<v-btn text>
								👎
							</v-btn>
						</v-card-actions>
					</v-card>
				</v-col>
			</v-row>
		</v-container>
	</div>
</template>

<script>
export default {
	name: 'History',
	data() {
		return {
			orders: [{
				name: "Cafe Badilico",
				rating: Math.round((Math.random() * (5 - 3) + 3) * 10) / 10,
				price: 53,
				people: 4,
				img: "https://cdn.vuetifyjs.com/images/cards/cooking.png",
				description: ""
			}, {
				name: "Restaurant Solvetchi",
				rating: Math.round((Math.random() * (5 - 3) + 3) * 10) / 10,
				price: 12,
				people: 1,
				img: "http://biarritz-pizza.fr/img-customer/configuration/5877a032cc3e8.35a3aaeb662bfd222e72443b23bd530b.jpeg",
				description: "Cuisine italienne, pizza, macaroni."
			}, {
				name: "La Brasserie Salée",
				rating: Math.round((Math.random() * (5 - 3) + 3) * 10) / 10,
				price: 89,
				people: 12,
				img: "https://images-ext-1.discordapp.net/external/Fefjr6PbFQQ1qW6EPYgF3LQNLsqsBMslTcFwHjZwClg/https/sauvetabouffe.org/wp-content/uploads/2020/02/Recettes_potluck_anti-gaspi.jpg",
				description: ""
			}, {
				name: "Bistro Régent",
				rating: Math.round((Math.random() * (5 - 3) + 3) * 10) / 10,
				price: 89,
				people: 12,
				img: "https://www.bistroregentbordeaux.fr/public/img/big/D804377jpg_5b2237451f325.jpg",
				description: "Une cuisine savoureuse au sein d’une ambiance décontractée."
			}, {
				name: "Santosha",
				rating: Math.round((Math.random() * (5 - 3) + 3) * 10) / 10,
				price: 89,
				people: 12,
				img: "https://images-ext-2.discordapp.net/external/7_VRlEKMizpK55lBRcEeRgBgfVR9B6Z4O7Sb884nXN4/https/maximumwallhd.com/wp-content/uploads/2017/01/wallpaper-image-nourriture-japon-17.jpg",
				description: "Cantine du Sud-Est asiatique pour tous. Inspiré par les saveurs de certains pays d’Asie."
			}]
		}
	}
}
</script>