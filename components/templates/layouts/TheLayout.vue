<template>
  <v-row wrap justify="center" class="pa-3">
    <v-col cols="12" sm="10" md="8" xl="7">
      <v-card class="pa-3">
        <slot name="TheContent" />
      </v-card>
    </v-col>
    <v-col v-if="$vuetify.breakpoint.mdAndUp" md="3" lg="2" xl="2" class="pa-3">
      <introduction-card />
      <article-list-card />
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
