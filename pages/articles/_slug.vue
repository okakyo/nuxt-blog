<template>
  <the-layout>
    <template #TheContent>
      <div class="pa-3 ma-4 article">
        <h1>{{ page.title }}</h1>
        <v-divider />
        <div>
          {{ page.discription }}
        </div>
        <nuxt-content class="my-5" :document="page" />
      </div>
    </template>
  </the-layout>
</template>

<script lang="ts">
import Vue from 'vue'
import TheLayout from '~/components/templates/layouts/TheLayout.vue'

export default Vue.extend({
  components: { TheLayout },
  async asyncData({ params, $content }) {
    const slug = params.slug
    const page = await $content(slug).fetch()
    return {
      page,
    }
  },
})
</script>
<style lang="scss">
.article {
  width: inherit;
  padding: 5%;
  padding-top: 2.5%;
  line-break: auto;
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
p {
  padding: 0.75em;
  padding-bottom: 0.25em;
  padding-top: 0.25em;
  line-height: 1.8em;
  white-space: pre-wrap;
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
