<template>
  <div>
    <h1>{{ page.title }}</h1>
    <v-divider />
    <div>
      {{ page.discription }}
    </div>
    <nuxt-content :document="page" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  async asyncData({ params, $content }) {
    const slug = params.slug
    const page = await $content(slug).fetch()
    return {
      page,
    }
  },
})
</script>
