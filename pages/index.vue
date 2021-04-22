<template>
  <the-layout>
    <template #TheContent>
      <v-card v-if="tagName" outlined class="mb-6 px-3">
        <v-card-title>Tags：{{ tagName }}</v-card-title>
      </v-card>
      <v-card outlined class="pa-3">
        <v-card-title>Article</v-card-title>
        <v-row v-if="articleList && articleList.length > 0" class="mx-2">
          <v-col
            v-for="(article, index) in articleList"
            :key="index"
            cols="12"
            sm="6"
          >
            <article-card class="mx-2" :article="article" />
          </v-col>
        </v-row>
        <v-card-title>Tutorial</v-card-title>
        <v-row class="mx-2">
          <v-col v-for="(i, index) in 6" :key="index" cols="6" md="4">
            <v-card class="mx-2" outlined>
              <v-card-title> sample </v-card-title>
            </v-card>
          </v-col>
        </v-row>
      </v-card>
    </template>
  </the-layout>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import TheLayout from '@/components/templates/layouts/TheLayout.vue'
import ArticleCard from '@/components/organisms/cards/ArticleCard.vue'
export default defineComponent({
  components: {
    TheLayout,
    ArticleCard,
  },
  async asyncData({ $content, query }) {
    const tagName = query.tag
    const articleList = await $content('articles', { deep: true })
      .only(['title', 'path', 'createdAt', 'updatedAt', 'tags', 'description'])
      .limit(6)
      .fetch()
    return {
      articleList,
      tagName,
    }
  },
})
</script>
