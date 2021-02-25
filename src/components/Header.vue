<template>
	<v-app-bar app color="white" elevation="0">
		<v-toolbar-title>
			<router-link to="/" class="buttons"
				>RollEat</router-link
			></v-toolbar-title
		>

		<v-spacer></v-spacer>

		<div v-if="loggedIn">
			<router-link to="/profile"
				>Coucou {{ userData.username }}</router-link
			>
		</div>
		<div v-else>
			<router-link to="/login" class="buttons">
				<v-btn>Connexion</v-btn>
			</router-link>

				<v-list-item link @click="logoutDialog = true">
					<v-list-item-icon>
						<v-icon>mdi-logout</v-icon>
					</v-list-item-icon>

					<v-list-item-content>
						<v-list-item-title>Déconnexion</v-list-item-title>
					</v-list-item-content>
				</v-list-item>

		<v-dialog v-model="logoutDialog" max-width="525">
			<v-card>
				<v-card-title class="headline">
					Voulez-vous vraiment vous déconnecter ?
				</v-card-title>
				<v-card-text>
					<img width="480" src="https://i.imgur.com/OI30Xvb.jpg" alt="Logout cat" />
				</v-card-text>
				<v-card-actions>
					<v-spacer></v-spacer>
					<v-btn color="green darken-1" text @click="logoutDialog = false">
						NON !
					</v-btn>
					<v-btn color="red darken-1" text @click="signOut(), (logoutDialog = false)">
						ui
					</v-btn>
				</v-card-actions>
			</v-card>
		</v-dialog>
</template>

<script>
export default {
	name: "Header",
	data() {
		return {
			loggedIn: false,
			userData: this.$models.user
		};
	},
			async signOut() {
				try {
					await this.$firebase.auth().signOut();
					this.$router.replace({
						path: "Login"
					});
				} catch (err) {
					console.log(err);
				}
				
			}
	created() {
		this.loggedIn = this.$firebase.auth().currentUser ? true : false;
		this.$db
			.collection("users")
			.doc(this.$firebase.auth().currentUser.uid)
			.onSnapshot(doc => {
				this.userData = {
					...this.$models.user,
					...doc.data(),
					id: doc.id
				};
			});
	}
};
</script>