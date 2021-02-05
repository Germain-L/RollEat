<template>
  <v-container justify="center">
    <v-col class="col-8 offset-2" justify="center" align="center">
      <h2>Inscription</h2>
      <v-text-field label="Pseudo"> </v-text-field>
      <v-text-field label="Email"> </v-text-field>
      <v-row class="align-content-center py-2">
        <v-col cols="12" lg="6" class="py-0">
          <v-text-field
            v-model="password"
            :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
            label="Mot de passe"
            :type="showPassword ? 'text' : 'password'"
            @click:append="showPassword = !showPassword"
          >
          </v-text-field>
        </v-col>
        <v-col cols="12" lg="6" class="py-0">
          <v-text-field
            v-model="password2"
            :append-icon="showPassword2 ? 'mdi-eye' : 'mdi-eye-off'"
            label="Confirmation de mot de passe"
            :type="showPassword2 ? 'text' : 'password'"
            @click:append="showPassword2 = !showPassword2"
          >
          </v-text-field>
        </v-col>
      </v-row>
      <CustomButton text="Connexion" />
    </v-col>
  </v-container>
</template>

<script>
import CustomButton from "@/components/Custom_button.vue";
export default {
  name: "Signup",
  components: {
    CustomButton,
  },

  methods: {
    verifyPassword: function () {
      if (this.password == this.password2) {
        console.log("password correct");
        return true;
      }
      return false;
    },
  },

  data() {
    return {
      password: "",
      password2: "",
      showPassword: false,
      showPassword2: false,
    };
  },
};
</script>

<style>
</style>