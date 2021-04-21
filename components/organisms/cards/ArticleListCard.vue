<template>
  <v-card outlined>
    <v-card-title> 最新記事一覧 </v-card-title>
    <v-divider />
    <article-list />
  </v-card>
</template>
<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import ArticleList from '~/components/molecules/lists/ArticleList.vue'
export default defineComponent({
  components: { ArticleList },
})
</script>
