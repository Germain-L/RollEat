<template>
	<v-footer>
		<v-col class="text-center" cols="12">
			<v-row justify="center">
				<v-col cols="3">
					<v-btn small class="col-auto mx-2" text to="/about">Qui sommes nous ?</v-btn>
				</v-col>
				<v-col cols="3">
					<v-btn small color="primary" class="col-auto mx-2" @click="contactDialog = true" text>Contact</v-btn>
				</v-col>

				<v-col cols="12">
					{{ new Date().getFullYear() }} — <strong>RollEat</strong>
				</v-col>
			</v-row>
		</v-col>
		<v-dialog v-model="contactDialog" max-width="525">
			<v-card>
				<v-card-title class="headline"> Contact </v-card-title>
				<v-card-text>
					<a href="mailto:exemple@gmail.com" target="_blank">
						<img width="480" src="https://cdn.dribbble.com/users/65451/screenshots/2142189/shake.gif" alt="Contact" />
					</a>
					<v-card-actions>
						<v-spacer></v-spacer>
						<v-btn color="red darken-1" text @click="contactDialog = false">
							Fermer
						</v-btn>
					</v-card-actions>
				</v-card-text>
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
				contactDialog: false
			};
		},
		created() {
			this.loggedIn = this.$firebase.auth().currentUser ? true : false;
		}
	};

</script>
