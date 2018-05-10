<template>
  <div>

    <div class="hero">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            HUMA
          </h1>
          <h2 class="subtitle">
            A blog about Humans & Machines
          </h2>
        </div>
      </div>
    </div>

    <div class="columns is-multiline" v-for="post in posts" v-bind:key="post.date">
      <div class="column is-4">
        <div class="card" v-for="post in posts" :key="post.date">
          <nuxt-link :to="post._path">
            <div class="card-image">
                 <img :src="post.thumbnail"/>
            </div>
            <div class="card-content">
              <div class="content">
                <p class="title">{{ post.title }}</p>
                <p class="subtitle">{{ post.summary }}</p>
              </div>
            </div>
          </nuxt-link>
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

<style>
div.card:hover {
  opacity: 0.8;
}
</style>
