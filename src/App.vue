<template>
  <v-app>
    <v-app-bar class="app-pokemon-bar" app color="primary" dark>
      <v-btn class="d-flex align-center" :to="{ name: 'pokemons' }" text>
        Pokemon
      </v-btn>
      <v-spacer></v-spacer>

      <v-btn href="https://pokeapi.co/" target="_blank" text>
        <span class="mr-2">
          PokeAPI
        </span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
    <v-content :style="bodyStyle">
      <router-view :key="$route.fullPath || '/'"></router-view>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "App",
  computed:{
    bodyStyle() {
      return {
        background: this.$route.fullPath === '/404' ? '#e5e5e5':'white'
      }
    }
  }
};
</script>
