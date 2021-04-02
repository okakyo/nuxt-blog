<template>
  <v-app dark>
    <the-header />
    <v-main app>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
import TheHeader from '@/components/molecules/headers/TheHeader.vue'

export default Vue.extend({
  components: {
    TheHeader,
  },
})
</script>
