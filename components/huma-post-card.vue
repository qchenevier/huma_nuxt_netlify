<template lang='pug'>
  .card
    nuxt-link(:to="post._path")
      .card-image
         img(:src="post.thumbnail")
      .card-content
        .content
          p.title {{ post.title }}
          p.subtitle {{ post.summary }}
</template>

<script>
export default {
  props: ['post']
};
</script>

<style scoped>
.card {
  margin: 10px;
}

.card:hover {
  opacity: 0.8;
}
</style>
