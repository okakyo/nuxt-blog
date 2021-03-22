<template>
  <v-row justify="center">
    <v-col v-if="$vuetify.breakpoint.mdAndUp" md="3" xl="4">
      <introduction-card />
      <article-list-card />
    </v-col>
    <v-col cols="12" sm="10" md="9" xl="8">
      <v-card height="90vh"> </v-card>
    </v-col>
  </v-row>
</template>
<script lang="ts">
import Vue from 'vue'
import ArticleListCard from '~/components/organisms/cards/ArticleListCard.vue'
import IntroductionCard from '~/components/organisms/cards/IntroductionCard.vue'
export default Vue.extend({
  components: { IntroductionCard, ArticleListCard },
})
</script>
