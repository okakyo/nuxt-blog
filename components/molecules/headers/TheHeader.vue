<template functional>
  <v-app-bar app>
    <v-app-bar-title> Kyoro Site </v-app-bar-title>
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
