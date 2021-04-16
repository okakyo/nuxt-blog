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
          text: 'Articles',
          disabled: false,
          to: '/articles',
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
<style lang="scss">
.article {
  width: inherit;
  padding: 5%;
  padding-top: 2.5%;
  line-break: auto;

  p {
    padding: 0.25em 0.75em;
    line-height: 1.8em;
    white-space: pre-wrap;
  }
}
.description {
  margin: 0.75em;
}
.nuxt-content {
  ul {
    margin-bottom: 1.5em;
    margin-left: 0.5em;
  }
  li {
    line-height: 2em;
    margin-block-end: 0.5em;
  }
  img {
    max-width: 90%;
    margin: 0.5rem;
  }
  pre {
    margin: 0.5rem 0;
    box-shadow: none;
  }
  code::before {
    content: initial;
  }
  code {
    margin: 0 0.3rem;
  }
}

.v-application code {
  background-color: #eee;
  color: #333;
  padding: 0.5em;
  font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, Courier,
    monospace;
}

.nuxt-content-highlight {
  pre {
    margin-top: 1em;
    margin-bottom: 1em;
  }
  code {
    padding: initial;
    font-size: initial;
    color: '#ccc';
  }
  pre code {
    background-color: transparent !important;
    color: #ccc;
    overflow-x: auto;
    overflow-y: auto;
    word-wrap: none;
  }
}
</style>
