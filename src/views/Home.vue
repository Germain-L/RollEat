<template>
	<div>
		<v-col align="center">
			<h1>Quel est le but de Roll Eat ?</h1>
			<v-container class="description">
				<p>
					Lorem ipsum dolor sit amet, consectetur adipiscing elit.
					Curabitur turpis amet urna sagittis, aliquam pulvinar. Id
					risus lorem pharetra sed. Id tempus aenean dolor, faucibus
					at donec sollicitudin. Ultrices tellus risus magna diam in
					praesent elementum aliquam curabitur.
				</p>
			</v-container>
			<v-img
				:src="require('../assets/slogan.png')"
				contain
				height="350"
			/>
			<v-container></v-container>
			<router-link to="/order" class="buttons">
				<v-btn>Commander</v-btn>
			</router-link>
		</v-col>
	</div>
</template>

<script>
export default {
	name: "Home"
};
</script>

<style scoped>
h1 {
	font-size: 50px;
	color: grey;
}

.description {
	width: 50%;
}
</style>
