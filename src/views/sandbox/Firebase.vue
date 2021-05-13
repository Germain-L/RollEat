<template>
	<div class="main">
		<h1>Test avec Firebase</h1>
		<p>N'hésites pas à regarder dans la console et dans le code ;)</p>.
		<v-btn @click="addDocument" color="success">Ajoute un document</v-btn>

		<br/>

		<v-row>
			<v-text-field v-model="delDoc"></v-text-field>
			<v-btn @click="delDocument" color="error">Supprimer ce document</v-btn>
		</v-row>
	</div>
</template>

<script>
export default {
	name: 'Firebase-Sandbox',
	data() {
		return {
			delDoc: ''
		}
	},
	methods: {
		addDocument(){
			this.$db.collection("test").add({
				addingDate: new Date()
			}).then((ref) => {
				console.log(`Le fichier ${ref.id} a bien été ajouté !`);
			});
		},

		delDocument(){
			if(!this.delDoc) return console.error(`Tu n'a pas spécifié l'identifiant du document`);

			this.$db.collection("test").doc(this.delDoc).delete().then(() => {
				console.log(`Le fichier ${this.delDoc} a bien été supprimé !`);

				this.delDoc = '';
			});
		}
	},
	created() {
		this.$db.collection("test").doc("abc").get().then((doc) => {
			console.log("@Firestore test/abc:", doc.data());
		});
	}
}
</script>
