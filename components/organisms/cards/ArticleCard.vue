<template>
  <v-card flat class="pa-2 ma-3">
    <v-list-item three-line nuxt :to="article.path">
      <v-list-item-avatar
        tile
        size="80"
        color="grey lighten-3"
        class="pa-3 my-auto"
      >
      </v-list-item-avatar>
      <v-list-item-content class="pa-5">
        <v-card-title class="mb-3">
          {{ article.title }}
        </v-card-title>
        <v-list-item-subtitle class="my-1">
          {{ article.description }}
        </v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
    <v-card-actions>
      <v-chip-group v-if="article.tags && article.tags.length > 0">
        <v-chip
          v-for="(item, index) in article.tags"
          :key="index"
          small
          :to="`/tag/${item}`"
        >
          {{ item }}
        </v-chip>
      </v-chip-group>
    </v-card-actions>
  </v-card>
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
