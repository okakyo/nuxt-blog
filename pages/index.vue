<template>
  <the-layouts>
    <template #TheContent>
      <v-row>
        <v-col
          v-for="article in articleList"
          :key="article.title"
          cols="12"
          lg="6"
        >
          <article-card :article-title="article.title"></article-card>
        </v-col>
      </v-row>
    </template>
  </the-layouts>
</template>

<script lang="ts">
import Vue from 'vue'
import ArticleCard from '~/components/organisms/cards/ArticleCard.vue'
import TheLayouts from '~/components/templates/layouts/TheLayout.vue'

export default Vue.extend({
  components: {
    TheLayouts,
    ArticleCard,
  },
  async asyncData({ $content }) {
    const articleList = await $content('articles', { deep: true }).fetch()
    console.log(articleList)
    return {
      articleList,
    }
  },
})
</script>
