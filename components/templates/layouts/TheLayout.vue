<template>
  <v-row wrap justify="center" class="pa-3">
    <v-col cols="12" sm="12" md="8" xl="6">
      <v-card outlined class="pa-3">
        <slot name="TheContent" />
      </v-card>
    </v-col>
    <v-col v-if="$vuetify.breakpoint.mdAndUp" md="3" xl="2" class="pa-3">
      <introduction-card />
      <article-list-card />
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import ArticleListCard from '~/components/organisms/cards/ArticleListCard.vue'
import IntroductionCard from '~/components/organisms/cards/IntroductionCard.vue'

export default defineComponent({
  name: 'TheLayout',
  components: { IntroductionCard, ArticleListCard },
})
</script>
