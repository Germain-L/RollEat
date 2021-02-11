<template>
	<v-app-bar app color="white" elevation="0">
		<v-toolbar-title>
			<router-link to="/" class="buttons">RollEat</router-link></v-toolbar-title
		>

		<v-spacer></v-spacer>

		<div v-if="loggedIn">
			<router-link to="/profile"
				>Coucou
				{{ $firebase.auth().currentUser.displayName }} !</router-link
			>
		</div>
		<div v-else>
			<router-link to="/login" class="buttons">
				<v-btn>Connexion</v-btn>
			</router-link>

			<v-divider class="mx-4" vertical></v-divider>

			<router-link to="/signup" class="buttons">
				<v-btn>Inscription</v-btn>
			</router-link>
		</div>
	</v-app-bar>
</template>

<script>
export default {
	name: "Header",
	data() {
		return {
			loggedIn: false
		};
	},
	created() {
		this.loggedIn = this.$firebase.auth().currentUser ? true : false;
	}
};
</script>

<style scoped>
.buttons {
	text-decoration: none;
}
</style>
