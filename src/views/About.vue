<template>
	<div class="about">
		<v-parallax src="https://i-sam.unimedias.fr/2018/04/02/istock-865306026.jpg" height="500">
			<div class="col-5">
				<h1>
					RollEat, c'est quoi ?
				</h1>
				<p>
					RollEat est une application gratuite qui permets sur un coup de tête, de pouvoir générer un repas aléatoire en fonction de vos goûts !<br />
					Notre algorithme prends en considération vos goûts et plats que vous préférez, mais aussi vos allergènes et ce que vous n'aimez pas.
				</p>
			</div>
		</v-parallax>
		<v-container>
			<v-row>
				<v-col cols="6">
					<h1>
						Comment fonctionne l'algorithme ?
					</h1>
					<p>Notre algorithme fonctionne de manière très simple en passant par trois phase distincte.</p>
					<ul>
						<li>
							<p>
								<span class="overline">Première phase : Votre plan de table</span><br />

								Pour commencer, RollEat va vous demander combien vous êtes, votre régime alimentaire (sain, moins sain, vegan, etc) et aussi vos allergènes et aliments que vous n'aimez pas.
							</p>
						</li>
						<li>
							<p>
								<span class="overline">Seconde phase : Première recherche de plats</span><br />

								Grâce aux informations fournies juste avant, RollEat va procéder à une première recherche qui servira surtout à éliminer les plats que vous ou vos convives n'aimez pas, ou les plats contenant des allergènes.
							</p>
						</li>
						<li>
							<p>
								<span class="overline">Troisième phase : Seconde recherche de plats</span><br />

								Une fois avoir retiré tous les plats que vous n'aimez pas, RollEat va maintenant sélectionner de manière aléatoire (toujours selon vos critères principaux) parmis les restaurateurs partenaires un menu.
							</p>
						</li>
						<li>
							<p>
								<span class="overline">Et voilà ! À table !</span><br />

								Tada ! Votre menu pour vous ou vos convives est généré, vous pouvez maintenant commander. Bon appétit ! 🍔
							</p>
						</li>
					</ul>
				</v-col>
				<v-col cols="6">
					<v-row>
						<v-col cols="12">
							<h1>
								D'où est venu l'idée ?
							</h1>
							<p>
								Cette idée, quelque peut spéciale, nous est venu du fait que souvent, on regarde UberEats ou autre quelconque application de livraison, mais on ne sait pas quoi choisir.
								C'est ainsi que le concept de RollEat est apparu.
							</p>
						</v-col>
						<v-col cols="12">
							<h1>
								Comment sont réalisés les paiements ?
							</h1>
							<p>
								Pour votre sécurité, tous les paiements sont opérés par une plateforme externe, Stripe.<br/>
								Ce qui fait qu'aucune données de carte bancaire n'est enregistré chez nous.
							</p>
						</v-col>
						<v-col cols="12">
							<h1>
								Qui sommes-nous ?
							</h1>
							<p>Nous sommes 6 étudiants en première année dans une école d'informatique, l'EPSI.</p>
						</v-col>
					</v-row>
				</v-col>
			</v-row>
		</v-container>
	</div>
</template>

<script>
export default {
	name: 'About',
}
</script>