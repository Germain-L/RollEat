<template>
  <v-app-bar app color="white" elevation="0">
    <v-toolbar-title> 
      <router-link to="/">RollEat</router-link></v-toolbar-title>

    <v-spacer></v-spacer>

    <router-link to="/login">Connexion</router-link>

    <v-divider class="mx-4" vertical></v-divider>

    <router-link to="/signup">Inscription</router-link>
  </v-app-bar>
</template>

<script>
export default {
  name: "Header",
};
</script>