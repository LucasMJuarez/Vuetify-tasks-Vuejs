<template>
  <v-container grid-list-md>
    <v-layout row wrap>
      <v-flex>
        <v-card class="mx-auto" max-width="400">
          <v-img
            class="white--text align-end"
            height="200px"
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          >
            <v-card-title>Fotos</v-card-title>
          </v-img>
          <v-card-subtitle class="pb-0">Number 10</v-card-subtitle>

          <v-card-text class="text--primary">
            <div>Whitehaven Beach</div>

            <div>Whitsunday Island, Whitsunday Islands</div>
          </v-card-text>
          <v-card-actions>
            <v-btn color="orange" @click="dialog = true" text>Share</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
      <v-flex>
        <v-card class="mx-auto" max-width="400">
          <v-img
            class="white--text align-end"
            height="200px"
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          >
            <v-card-title>Fotos</v-card-title>
          </v-img>
          <v-card-subtitle class="pb-0">Number 10</v-card-subtitle>

          <v-card-text class="text--primary">
            <div>Whitehaven Beach</div>
            <div>Whitsunday Island, Whitsunday Islands</div>
          </v-card-text>
          <v-card-actions>
            <v-btn color="orange" @click="dialog = true" text>Share</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
      <v-flex>
        <v-card class="mx-auto" max-width="400">
          <v-img
            class="white--text align-end"
            height="200px"
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          >
            <v-card-title>Fotos</v-card-title>
          </v-img>
          <v-card-subtitle class="pb-0">Number 10</v-card-subtitle>
          <v-card-text class="text--primary">
            <div>Whitehaven Beach</div>
            <div>Whitsunday Island, Whitsunday Islands</div>
          </v-card-text>
          <v-card-actions>
            <v-btn color="orange" @click="dialog = true" text>Share</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
      <v-flex>
        <v-card class="mx-auto" max-width="400">
          <v-img
            class="white--text align-end"
            height="200px"
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          >
            <v-card-title>Fotos</v-card-title>
          </v-img>
          <v-card-subtitle class="pb-0">Number 10</v-card-subtitle>
          <v-card-text class="text--primary">
            <div>Whitehaven Beach</div>
            <div>Whitsunday Island, Whitsunday Islands</div>
          </v-card-text>
          <v-card-actions>
            <v-btn color="orange" @click="dialog = true" text>Share</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>

    <v-dialog v-model="dialog" persistent max-width="500px" transition="dialog-transition">
      <v-card>
        <v-card-title primary-title>title</v-card-title>
        <v-card-text>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Fugiat at iure dolorum vitae odit reprehenderit totam inventore, esse maiores quis porro ipsum accusamus in! Ea magni itaque officiis provident commodi.</v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn @click="dialog = false">Cerrar</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
export default {
  name: "Card",
  data: () => {
    return {
      dialog: false
    };
  }
};
</script>
    
    
