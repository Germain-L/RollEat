<template>
  <v-app>
    <Header />
    <v-main>
    <v-divider></v-divider>
      <Home />
    </v-main>
    <v-divider></v-divider>
    <Footer />
  </v-app>
</template>

<script>
import Home from "./views/Home";
import Header from "./components/Header";
import Footer from "./components/Footer";

export default {
  name: "App",

  components: {
    Home,
    Header,
    Footer,
  },

  data: () => ({
    //
  }),
};
</script>
