<template lang='pug'>
  div.columns.is-multiline
    div.column.is-5
      figure.image
        img(:src="`${thumbnail}`")
      p#post-side.title {{ title }}
      p#post-side.subtitle {{ summary }}
    div.column.is-7(style="overflow:auto")
      vue-markdown {{ body }}
</template>

<script>
import VueMarkdown from 'vue-markdown'

export default {
  async asyncData({ params }) {
    let post = await import('~/content/blog/posts/' + params.slug + '.json');
    return post;
  },
  components: {
      VueMarkdown
  }
};

</script>

<style>
p#post-side {
  margin: 20px;
}
</style>
