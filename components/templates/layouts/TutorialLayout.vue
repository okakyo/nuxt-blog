<template>
  <v-container>
    <v-row wrap justify="center">
      <v-col v-if="$vuetify.breakpoint.mdAndUp" cols="3">
        <v-list> </v-list>
      </v-col>
      <v-col cols="12" md="9" lg="8" xl="6">
        <slot name="TheContent" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  name: '',
})
</script>
