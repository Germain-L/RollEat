<template>
  <v-container justify="center">
      <v-col justify="center" align="center">
          <h2> Connexion </h2>
          <v-text-field label="Email">
            
          </v-text-field>
          <v-text-field 
            :append-icon= "showPassword? 'mdi-eye': 'mdi-eye-off' " 
            label="Password"
            :type= "showPassword? 'text': 'password' "
            @click:append="showPassword = !showPassword">
           </v-text-field>
            <CustomButton text="Connexion"/>
            <router-link to="/signup">
            <p>Je n'ai pas de compte </p>
            </router-link>
      </v-col>
  </v-container>
</template>

<script>

import CustomButton from "@/components/Custom_button.vue"
export default {
    name: 'Login',
    components: {
        CustomButton
    },

    data() {
        return {
            showPassword:false,
        }
    }

}
</script>

<style scoped>

h2 {
    text-align: center;
}

.v-btn {
    margin: 25px;
}

</style>