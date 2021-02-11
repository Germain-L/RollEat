<template>
	<v-footer color="white">
		<v-col class="text-center" cols="12">
			<v-row justify="center">
				<v-btn small class="col-auto mx-2">Qui sommes nous ?</v-btn>
				<v-btn small class="col-auto mx-2">Contact</v-btn>
				<v-btn
					small
					color="warning"
					class="col-auto mx-2"
					v-show="loggedIn"
					@click="dialog = true"
					>Se déconnecter 🥺</v-btn
				>
			</v-row>
			<br />
			{{ new Date().getFullYear() }} — <strong>RollEat</strong>
		</v-col>

		<v-dialog v-model="dialog" max-width="525">
			<v-card>
				<v-card-title class="headline">
					Voulez-vous vraiment vous déconnecter ?
				</v-card-title>
				<v-card-text>
					<img
						width="480"
						src="https://i.imgur.com/OI30Xvb.jpg"
						alt="Logout cat"
					/>
				</v-card-text>
				<v-card-actions>
					<v-spacer></v-spacer>
					<v-btn color="green darken-1" text @click="dialog = false">
						NON !
					</v-btn>
					<v-btn
						color="red darken-1"
						text
						@click="signOut(), (dialog = false)"
					>
						ui
					</v-btn>
				</v-card-actions>
			</v-card>
		</v-dialog>
	</v-footer>
</template>

<script>
export default {
	name: "Footer",
	data() {
		return {
			loggedIn: false,
			dialog: false
		};
	},
	methods: {
		async signOut() {
			try {
				await this.$firebase.auth().signOut();
				this.$router.replace({
					path: "Login"
				});
			} catch (err) {
				console.log(err);
			}

			console.log("T'ES DECO BOLOSSSSSS");
		}
	},
	created() {
		this.loggedIn = this.$firebase.auth().currentUser ? true : false;
	}
};
</script>

<style scoped>
p {
	font-size: 18px;
	padding: 1em;
}
</style>
