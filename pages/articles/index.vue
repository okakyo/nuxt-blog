<template>
  <the-layout>
    <template #TheContent>
      <v-card min-height="85vh" outlined class="pa-3">
        <v-row>
          <v-col
            v-for="article in articleList"
            :key="article.title"
            cols="12"
            md="6"
          >
            <article-card :article="article" />
          </v-col>
        </v-row>
        <v-pagination :length="countAllArticles" />
      </v-card>
    </template>
  </the-layout>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import ArticleCard from '@/components/organisms/cards/ArticleCard.vue'
import TheLayout from '~/components/templates/layouts/TheLayout.vue'
export default defineComponent({
  components: {
    TheLayout,
    ArticleCard,
  },
  async asyncData({ $content, query }) {
    const page: number = Number(query.page)

    const [getAllArticles, articleList] = await Promise.all([
      $content('articles', { deep: true }).only(['title']).fetch(),
      $content('articles', { deep: true })
        .only(['title', 'path', 'updatedAt', 'tags', 'description'])
        .limit(10)
        .skip(10 * page)
        .fetch(),
    ])
    const countAllArticles: number = Math.ceil(getAllArticles.length / 6)
    return {
      articleList,
      countAllArticles,
    }
  },
})
</script>

TheLayout
