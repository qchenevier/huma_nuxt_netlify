<template>
  <div class="columns is-multiline">
    <div class="column is-5">
      <figure class="image">
        <img :src="`${thumbnail}`">
      </figure>
      <p class="title">{{ title }}</p>
      <p class="subtitle">{{ summary }}</p>
    </div>
    <div class="column is-7"  style="overflow:auto">
      <vue-markdown> {{ body }} </vue-markdown>
    </div>
  </div>
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
p.title, p.subtitle {
  margin: 10px;
}
</style>
