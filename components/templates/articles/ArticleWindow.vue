<template>
  <div>
    <v-breadcrumbs nuxt :items="urlItems" />
    <div class="pa-3 ma-4 article">
      <h1>{{ page.title }}</h1>
      <v-divider class="my-2" />
      <div class="description">
        {{ page.description }}
      </div>
      <nuxt-content class="my-5" :document="page" />
    </div>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  props: {
    urlItems: {
      type: Array,
      required: true,
      default: () => {},
    },
    page: {
      type: Object,
      required: true,
      default: () => {},
    },
  },
})
</script>
