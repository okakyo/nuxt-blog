<template>
  <v-card outlined class="mb-3">
    <v-card-title>
      <v-avatar size="56">
        <img alt="user" :src="require('~/assets/myImg.png')" />
      </v-avatar>
      <p class="ml-6 mt-4">OkaKyo</p>
    </v-card-title>
    <v-card-text> Web アプリ開発を勉強してます。 </v-card-text>
    <v-card-actions>
      <v-btn v-for="item in actions" :key="item.icon" :href="item.to" icon>
        <v-icon>
          {{ item.icon }}
        </v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api'
import { mdiTwitter, mdiGithub, mdiPost } from '@mdi/js'
export default defineComponent({
  setup() {
    const actions = ref([
      {
        icon: mdiTwitter,
        to: 'https://twitter.com/31415O_Kyo',
      },
      {
        icon: mdiGithub,
        to: 'https://github.com/okakyo',
      },
      {
        icon: mdiPost,
        to: 'https://okakyo-new-portfolio.netlify.app/',
      },
    ])
    return {
      actions,
    }
  },
})
</script>
