<template>
  <v-footer color="white">
    <v-col class="text-center" cols="12">
      <v-row justify="center">
        <p>Qui sommes nous ?</p>
        <p>Contact</p>
      </v-row>
      {{ new Date().getFullYear() }} — <strong>RollEat</strong>
    </v-col>
  </v-footer>
</template>


<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
p {
    font-size: 18px;
    padding: 1em;
}
</style>