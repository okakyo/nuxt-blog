<template>
  <the-layout>
    <template #TheContent>
      <v-card outlined class="pa-3">
        <v-row>
          <v-col cols="12" md="6">
            <tutorial-list-card />
          </v-col>
        </v-row>
      </v-card>
    </template>
  </the-layout>
</template>

<script>
import TutorialListCard from '~/components/organisms/cards/TutorialListCard.vue'
import TheLayout from '~/components/templates/layouts/TheLayout.vue'
export default {
  components: { TheLayout, TutorialListCard },
}
</script>
