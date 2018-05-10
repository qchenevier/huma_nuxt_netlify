<template lang='pug'>
  div

    div.hero
      div.hero-body
        div.container
          h1.title HUMA
          h2.subtitle A blog about Humans & Machines

    div.columns.is-multiline(v-for="post in posts" v-bind:key="post.date")
      div.column.is-4
        div.card(v-for="post in posts" :key="post.date")
          nuxt-link(:to="post._path")
            div.card-image
               img(:src="post.thumbnail")
            div.card-content
              div.content
                p.title {{ post.title }}
                p.subtitle {{ post.summary }}
</template>

<script>
export default {
  data() {
    // Using webpacks context to gather all files from a folder
    const context = require.context('~/content/blog/posts/', false, /\.json$/);

    // Posts URLs are based on json filenames without extension
    const posts = context.keys().map(key => ({
      ...context(key),
      _path: `/blog/${key.replace('.json', '').replace('./', '')}`
    }));

    return { posts };
  }
};
</script>

<style>
div.card:hover {
  opacity: 0.8;
}
</style>
