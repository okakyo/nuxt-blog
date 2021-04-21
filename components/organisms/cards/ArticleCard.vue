<template>
  <div>
    <v-card flat nuxt :to="article.path">
      <v-img
        :src="article.img ? article.img : require('~/assets/noImg.png')"
        aspect-ratio="2"
      />
      <div class="d-flex flex-no-wrap">
        <div>
          <v-card-title style="font-size: 1rem" class="py-5">{{
            article.title
          }}</v-card-title>
          <v-card-subtitle class="py-3">{{
            article.updatedAt
          }}</v-card-subtitle>
        </div>
      </div>
    </v-card>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  name: 'ArticleCard',
  props: {
    article: {
      type: Object,
      required: true,
      default: () => {},
    },
  },
})
</script>
