<template>
  <v-app-bar app>
    <h2 class="">Kyoro Site</h2>
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
