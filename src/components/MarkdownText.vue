<template>
  <div class="MarkdownText s-content"
    v-html="html"
  />
</template>

<script>
import marked from 'marked';

export default {
  name: `MarkdownText`,
  props: {
    md: {
      default: ``,
      required: true,
      type: String,
    },
  },
  computed: {
    html() {
      return marked(this.md);
    },
  },
};
</script>
