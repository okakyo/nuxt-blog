<template>
  <div>
    <v-card-title>Article</v-card-title>
    <v-row v-if="articleList && articleList.length > 0" class="mx-2">
      <v-col
        v-for="article in articleList"
        :key="article.title"
        cols="12"
        sm="6"
        xl="4"
      >
        <article-card class="mx-2" :article="article" />
      </v-col>
    </v-row>
    <div class="my-9" style="text-align: center">
      <link-button to="/articles" text="他のブログ記事はコチラ" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import ArticleCard from '@/components/organisms/cards/ArticleCard.vue'
import LinkButton from '@/components/molecules/buttons/LinkButton.vue'
export default defineComponent({
  components: {
    ArticleCard,
    LinkButton,
  },
  props: {
    articleList: {
      type: Array,
      required: true,
      default: () => {},
    },
  },
})
</script>
