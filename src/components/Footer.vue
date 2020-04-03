<template>
  <v-container>
    <v-footer>
      <v-card flat tile width="100%" class="green text-center">
        <v-card-text>
          <v-btn v-for="icon in icons" :key="icon" class="mx-4" icon>
            <v-icon size="24px">{{ icon }}</v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="white--text">
          {{ new Date().getFullYear()}} -
          <strong>Villa Maria - Córdoba</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-container>
</template>

name: "Footer"

<script>
export default {
  name: "Footer",

  data: () => ({
    icons: ["mdi-home", "mdi-delete"],

    padless: false,
    variant: "default"
  })
};
</script>