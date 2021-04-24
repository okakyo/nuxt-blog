<template>
  <v-app>
    <the-header />
    <v-main app class="grey lighten-4">
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer color="grey lighten-2"> </v-footer>
  </v-app>
</template>

<script lang="ts">
import TheHeader from '@/components/molecules/headers/TheHeader.vue'
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  components: {
    TheHeader,
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start()

      setTimeout(() => this.$nuxt.$loading.finish(), 500)
    })
  },
})
</script>
