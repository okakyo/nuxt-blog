<template>
  <v-app-bar app>
    <v-app-bar-title> Kyoro Site </v-app-bar-title>
    <v-btn text exact to="/"></v-btn>
    <v-spacer />
    <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
  </v-app-bar>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      drawer: false,
    }
  },
})
</script>
