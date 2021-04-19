<template>
  <the-layout>
    <template #TheContent>
      <article-window :page="page" :url-items="urlItems" />
    </template>
  </the-layout>
</template>

<script>
import { defineComponent } from '@vue/composition-api'
import ArticleWindow from '@/components/templates/articles/ArticleWindow.vue'
import TheLayout from '~/components/templates/layouts/TheLayout.vue'

export default defineComponent({
  components: { TheLayout, ArticleWindow },
  async asyncData({ params, $content }) {
    const slug = params.slug
    const page = await $content(`articles/${slug}`).fetch()
    return {
      page,
    }
  },
  computed: {
    urlItems() {
      return [
        {
          text: 'Home',
          disabled: false,
          to: '/',
        },
        {
          text: '記事一覧',
          disabled: false,
          to: '/articles/',
          exact: true,
        },
        {
          text: this.page.title,
          disabled: true,
          to: `/articles/${this.page.slug}`,
        },
      ]
    },
  },
})
</script>
