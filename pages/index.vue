<template>
  <the-layout>
    <template #TheContent>
      <v-row v-if="articleList && articleList.length > 0">
        <v-col
          v-for="(article, index) in articleList"
          :key="index"
          cols="12"
          lg="6"
        >
          <article-card :article="article" />
        </v-col>
      </v-row>
    </template>
  </the-layout>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import ArticleCard from '~/components/organisms/cards/ArticleCard.vue'
import TheLayout from '~/components/templates/layouts/TheLayout.vue'
export default defineComponent({
  components: {
    TheLayout,
    ArticleCard,
  },
  async asyncData({ $content }) {
    const articleList = await $content('articles', { deep: true })
      .only(['title', 'path', 'createdAt', 'updatedAt', 'tags'])
      .fetch()
    return {
      articleList,
    }
  },
})
</script>
