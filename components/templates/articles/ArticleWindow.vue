<template>
  <v-card outlined>
    <v-breadcrumbs nuxt :items="urlItems" />
    <div class="pa-3 ma-4 article">
      <h1>{{ page.title }}</h1>
      <v-divider class="my-2" />
      <div class="description">
        {{ page.description }}
      </div>
      <nuxt-content class="my-5" :document="page" />
    </div>
  </v-card>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  props: {
    urlItems: {
      type: Array,
      required: true,
      default: () => {},
    },
    page: {
      type: Object,
      required: true,
      default: () => {},
    },
  },
})
</script>
<style lang="scss">
.article {
  width: inherit;
  padding: 5%;
  padding-top: 2.5%;
  line-break: auto;

  p {
    padding: 0.25em 0;
    line-height: 1.8em;
    white-space: pre-wrap;
  }
}
.description {
  margin: 1.5em 0;
}
.nuxt-content {
  h2 {
    margin-top: 1em;
    margin-bottom: 1em;
  }
  h3 {
    margin-top: 1.25em 0;
    margin-bottom: 0.75em;
  }
  h4,
  h5,
  h6 {
    margin-top: 1.5em;
    margin-bottom: 0.5em;
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-weight: 700;
    line-height: 1.5;
    outline: 0;
  }

  table {
    border-collapse: collapse;
    margin: 1.5em 0.5em;
    display: block;
    overflow: auto;
    border-left: 1px solid #ddd;
  }

  tbody tr:nth-child(odd) {
    background-color: #e6e6e6;
  }
  th {
    font-weight: bold;
    background-color: #fff;
    border-top: 1px solid #ddd;
    border-bottom: 1px solid #ccc;
    border-right: 1px solid #ccc;
    padding: 8px 10px;
  }

  td {
    border-bottom: 1px solid #ccc;
    border-right: 1px solid #ccc;
    padding: 8px 10px;
    max-width: 600px;
  }

  th,
  td {
    padding: 5px 10px;
    display: table-cell;
    vertical-align: inherit;
  }

  ul {
    margin-bottom: 1.5em;
    margin-left: 0.5em;
  }
  li {
    line-height: 2em;
    margin-block-end: 0.5em;
  }
  img {
    max-width: 90%;
    margin: 0.5rem;
  }
  pre {
    margin: 0.5rem 0;
    box-shadow: none;
  }
  code::before {
    content: initial;
  }
  code {
    margin: 0 0.3rem;
  }

  hr {
    margin: 2.5em 0;
  }
  blockquote {
    border-left: 5px solid #ddd;
    color: #777;
    padding: 0.5em;
    margin: 1.5em 0;
  }
}

.v-application code {
  background-color: #eee;
  color: #333;
  padding: 0.5em;
  font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, Courier,
    monospace;
}

.nuxt-content-highlight {
  pre {
    margin-top: 1em;
    margin-bottom: 1em;
  }
  code {
    padding: initial;
    font-size: initial;
    color: '#ccc';
  }
  pre code {
    background-color: transparent !important;
    color: #ccc;
    overflow-x: auto;
    overflow-y: auto;
    word-wrap: none;
  }
}
</style>
