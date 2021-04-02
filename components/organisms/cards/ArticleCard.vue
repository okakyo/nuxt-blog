<template>
  <v-card outlined class="pa-2">
    <v-list-item three-line :to="`/articles/${articleSlug}`">
      <v-list-item-avatar
        tile
        size="90"
        color="grey"
        class="pa-3"
      ></v-list-item-avatar>
      <v-list-item-content class="pa-5">
        <v-list-item-title class="headline mb-1">
          {{ articleTitle }}
        </v-list-item-title>
        <v-list-item-subtitle>{{ articleDate }}</v-list-item-subtitle>
        <v-chip-group v-if="articleTags.length > 0">
          <v-chip
            v-for="(tag, index) in articleTags"
            :key="index"
            :to="`/tag/${item.tag}`"
          >
            {{ item.name }}
          </v-chip>
        </v-chip-group>
      </v-list-item-content>
    </v-list-item>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'ArticleCard',
  props: {
    articleTitle: {
      type: String,
      default: 'sample',
    },
    articleDate: {
      type: Date,
      default: () => {
        return new Date()
      },
    },
    articleTags: {
      type: Array,
      default: () => {
        return []
      },
    },
    articleSlug: {
      type: String,
      required: false,
      default: 'sample',
    },
  },
})
</script>
