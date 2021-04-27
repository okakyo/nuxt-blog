<template functional>
  <v-app-bar app class="green lighten-2 pa-2">
    <nuxt-link
      to="/"
      style="text-decoration: none"
      class="headline white--text"
    >
      Kyoro Site
    </nuxt-link>
    <v-spacer />
  </v-app-bar>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  data() {
    return {
      drawer: false,
    }
  },
})
</script>
