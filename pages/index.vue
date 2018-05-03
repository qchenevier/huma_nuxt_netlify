<template>
  <div>
    <div class="columns is-multiline" v-for="post in posts" v-bind:key="post.date">
      <div class="column is-4">
        <div class="card" v-for="post in posts" v-bind:key="post.date">
          <div class="card-image">
            <img v-bind:src="post.thumbnail">
          </div>
          <div class="content">
            <p class="title">{{ post.title }}</p>
            <p class="subtitle">{{ post.summary }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
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
