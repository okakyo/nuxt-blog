<template>
  <v-card>
    <v-card-title> 最新記事一覧 </v-card-title>
    <v-divider />
    <article-list />
  </v-card>
</template>
<script lang="ts">
import Vue from 'vue'
import ArticleList from '~/components/molecules/lists/ArticleList.vue'
export default Vue.extend({
  components: { ArticleList },
})
</script>
