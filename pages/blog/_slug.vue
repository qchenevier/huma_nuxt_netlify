<template>
  <article>
    <h1>{{ title }}</h1>
    <vue-markdown> {{ body }} </vue-markdown>
  </article>
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
