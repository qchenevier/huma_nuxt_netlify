<template lang='pug'>
  div
    .hero
      .hero-body
        .container
          h1.title HUMA
          h2.subtitle A blog about Humans & Machines

    .columns.is-multiline.is-gapless
      .column.is-4(v-for="post in sort_posts(posts, 'date').reverse()" :key="post.date")
        huma-post-card(:post="post")
</template>

<script>
import HumaPostCard from '~/components/huma-post-card.vue'
import _ from 'underscore'

export default {
  components: {
    HumaPostCard
  },
  data() {
    // Using webpacks context to gather all files from a folder
    const context = require.context('~/content/blog/posts/', false, /\.json$/);

    // Posts URLs are based on json filenames without extension
    const posts = context.keys().map(key => ({
      ...context(key),
      _path: `/blog/${key.replace('.json', '').replace('./', '')}`
    }));
    return { posts };
  },
  methods: {
    sort_posts(posts, sortKey) {
      return _.sortBy(posts, sortKey)
    }
  }
};
</script>

<style scoped>
.columns {
  margin: 10px;
}
</style>
