<template>
  <div>
    <v-card-title>Tutorial</v-card-title>
    <v-row>
      <v-col v-for="(i, index) in 6" :key="index" cols="6" lg="4">
        <tutorial-list-card />
      </v-col>
    </v-row>
    <div class="my-9" style="text-align: center">
      <link-button to="/tutorials" text="他のチュートリアルはコチラ" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import TutorialListCard from '@/components/organisms/cards/TutorialListCard.vue'
import LinkButton from '@/components/molecules/buttons/LinkButton.vue'
export default defineComponent({
  components: {
    TutorialListCard,
    LinkButton,
  },
})
</script>
