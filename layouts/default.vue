<template>
  <v-app>
    <the-header />
    <v-main app class="grey lighten-4">
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import TheHeader from '@/components/molecules/headers/TheHeader.vue'
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  components: {
    TheHeader,
  },
})
</script>
