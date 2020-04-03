<template>
  <v-container grid-list-xs app>
    <v-toolbar class="success">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-center">Lista de Tareas y Tarjetas</v-toolbar-title>
    </v-toolbar>

    <v-navigation-drawer app v-model="drawer" temporary>
      <v-layout mt-4 column align-center>
        <v-flex>
          <v-avatar color="red">
            <img src="https://randomuser.me/api/portraits/men/85.jpg" alt="alt" />
          </v-avatar>
        </v-flex>
        <v-flex>
          <p class="mt-3 headline">Lucas Juarez</p>
        </v-flex>
      </v-layout>
      <v-layout column>
        <v-flex mx-3>
          <v-btn color="success" block :to="{name: 'Home'}">Home</v-btn>
          <v-btn color="success" block :to="{name: 'tareas-crud'}">Lista de Tareas</v-btn>
        </v-flex>
      </v-layout>
    </v-navigation-drawer>
  </v-container>
</template>


<script>
export default {
  name: "NavBar",

  data() {
    return {
      drawer: false
    };
  }
};
</script>