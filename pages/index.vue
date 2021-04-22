<template>
  <the-layout>
    <template #TheContent>
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
      <v-row>
        <v-col cols="6" md="4">
          <v-card flat>
            <v-card-title> sample </v-card-title>
          </v-card>
        </v-col>
      </v-row>
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
  async asyncData({ $content }) {
    const articleList = await $content('articles', { deep: true })
      .only(['title', 'path', 'createdAt', 'updatedAt', 'tags', 'description'])
      .limit(6)
      .fetch()
    return {
      articleList,
    }
  },
})
</script>
