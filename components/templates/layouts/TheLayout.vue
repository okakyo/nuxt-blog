<template>
  <v-row wrap justify="center" class="pa-3">
    <v-col m cols="12" sm="12" md="8" xl="6">
      <slot name="TheContent" />
    </v-col>
    <v-col v-if="$vuetify.breakpoint.mdAndUp" md="3" xl="2" class="pa-3">
      <introduction-card />
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import IntroductionCard from '~/components/organisms/cards/IntroductionCard.vue'

export default defineComponent({
  name: 'TheLayout',
  components: { IntroductionCard },
})
</script>
