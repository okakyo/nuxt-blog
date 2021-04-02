<template>
  <v-card class="mb-3">
    <v-card-title>
      <v-avatar size="56">
        <img
          alt="user"
          src="https://pbs.twimg.com/profile_images/1322558610224812033/uae_BIjz_400x400.png"
        />
      </v-avatar>
      <p class="ml-6 mt-4">OkaKyo</p>
    </v-card-title>
    <v-card-text> Web アプリ開発を勉強してます。 </v-card-text>
    <v-card-actions>
      <v-btn v-for="item in actions" :key="item.icon" icon>
        <v-icon>
          {{ item.icon }}
        </v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      actions: [
        {
          icon: 'mdi-twitter',
          color: '',
          to: 'https://twitter.com/31415O_Kyo',
        },
        {
          icon: 'mdi-github',
          color: '',
          to: 'https://github.com/okakyo',
        },
        {
          icon: 'mdi-post',
          color: '',
          to: 'https://okakyo-new-portfolio.netlify.app/',
        },
      ],
    }
  },
})
</script>
