<template lang='pug'>
  .card
    nuxt-link(:to="post._path")
      .card-image
         img(:src="post.thumbnail")
      .card-content
        .content(v-if="post.tags")
          b-taglist(v-for="tag in post.tags" :key="tag.name")
            b-tag {{ tag.name }}
        .content
          p.title {{ post.title }}
          p.subtitle {{ post.summary }}
          p {{ reading_time.text }} | {{ pretty_date }}
</template>

<script>
import readingTime from 'reading-time'
import moment from 'moment'

export default {
  props: ['post'],
  data () {
    let reading_time = readingTime(this.post.body)
    let pretty_date = moment(this.post.date).format("MMMM YYYY")
    return {
      reading_time: reading_time,
      pretty_date: pretty_date
    }
  }
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
