<template>
  <article>
    <div class="column is-9 is-offset-1">
      <div class="card">
        <div class="card-image">
          <figure class="image">
            <img :src="`${thumbnail}`">
          </figure>
        </div>
        <div class="card-content">
          <div class="content">
            <p class="title">{{ title }}</p>
            <vue-markdown> {{ body }} </vue-markdown>
          </div>
        </div>
      </div>

    </div>
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
