<template>
  <the-layout>
    <template #TheContent>
      <div>
        <h1>{{ page.title }}</h1>
        <v-divider />
        <div>
          {{ page.discription }}
        </div>
        <nuxt-content :document="page" />
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
