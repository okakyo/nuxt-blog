<template>
  <the-layouts>
    <template #TheContent>
      <article-card v-for="i in 10" :key="i"></article-card>
    </template>
  </the-layouts>
</template>

<script lang="ts">
import Vue from 'vue'
import ArticleCard from '~/components/organisms/cards/ArticleCard.vue'
import TheLayouts from '~/components/templates/layouts/TheLayouts.vue'

export default Vue.extend({
  components: {
    TheLayouts,
    ArticleCard,
  },
})
</script>
