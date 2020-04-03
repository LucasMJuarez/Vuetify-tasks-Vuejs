<template>
  <v-container grid-list-xs>
    <NavBar />
    <Card />
    <Footer />
  </v-container>
</template>

<script>
// @ is an alias to /src

import Card from "@/components/Card.vue";
import NavBar from "@/components/NavBar.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Home",
  components: {
    NavBar,
    Card,
    Footer
  }
};
</script>
