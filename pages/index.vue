<template>
  <the-layout>
    <template #TheContent>
      <v-card v-if="tagName" outlined class="mb-6 px-3">
        <v-card-title>Tags：{{ tagName }}</v-card-title>
      </v-card>
      <v-card outlined class="pa-3">
        <article-list-window :article-list="articleList" />
      </v-card>
    </template>
  </the-layout>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import TheLayout from '@/components/templates/layouts/TheLayout.vue'
import ArticleListWindow from '@/components/templates/Index/ArticleListWindow.vue'
export default defineComponent({
  components: {
    TheLayout,
    ArticleListWindow,
  },
  async asyncData({ $content, query }) {
    const tagName = query.tag
    const articleList = await $content('articles', { deep: true })
      .only(['title', 'path', 'updatedAt', 'tags', 'description'])
      .limit(6)
      .fetch()

    return {
      articleList,
      tagName,
    }
  },
})
</script>
