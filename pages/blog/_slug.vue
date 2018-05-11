<template lang='pug'>
  .columns.is-multiline.is-centered
    .column.is-5
      .image.post-side
        img(:src="`${post.thumbnail}`")
      p.title.post-side {{ post.title }}
      p.subtitle.post-side {{ post.summary }}
    .column.is-7
      vue-markdown.post {{ post.body }}
    .column.is-10
      vue-disqus.comments(
        :shortname="disqusShortname"
        :identifier="disqusPageId"
        :url="disqusURL"
      )
</template>

<script>
import VueMarkdown from 'vue-markdown'

export default {
  data () {
    let disqusShortname = 'huma-io'
    return {
      disqusShortname: disqusShortname,
      disqusPageId: `${process.env.NODE_ENV}-${disqusShortname}-${this.$route.params.slug}`,
      disqusURL: `${process.env.baseUrl}${this.$route.fullPath}`
    }
  },
  async asyncData({ params }) {
    let post = await import('~/content/blog/posts/' + params.slug + '.json');
    return {
      post: post
    }
  },
  components: {
      VueMarkdown
  }
};

</script>

<style>
.post-side, .post, .comments {
  margin: 10px;
}
</style>
