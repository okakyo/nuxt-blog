<template>
  <v-btn nuxt text :to="to" :href="href" color="primary">
    {{ text }}
    <v-icon color="primary">
      {{ arrowIcon }}
    </v-icon>
  </v-btn>
</template>
<script>
import { defineComponent, ref } from '@vue/composition-api'
import { mdiArrowTopRight } from '@mdi/js'
export default defineComponent({
  props: {
    href: {
      type: String,
      required: false,
      default: '',
    },
    to: {
      type: String,
      required: false,
      default: '',
    },
    text: {
      type: String,
      required: false,
      default: '',
    },
  },
  setup() {
    const arrowIcon = ref(mdiArrowTopRight)
    return {
      arrowIcon,
    }
  },
})
</script>
