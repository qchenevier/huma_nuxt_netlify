<template>
  <navbar class="navbar container is-fixed-top">

    <div class="navbar-brand">

      <a href="http://huma.io">
        <figure class="image is-96x96 huma_logo" href="http://huma.io">
          <img src="~/assets/huma_logo.svg"/>
        </figure>
      </a>

      <div
        class="navbar-burger"
        @click="showNav = !showNav"
        :class="{'is-active': showNav}"
        style="height: 104px;"
      >
        <span></span>
        <span></span>
        <span></span>
      </div>

    </div>

    <div
      class="navbar-menu"
      :class="{'is-active': showNav}"
    >

      <div class="navbar-start">
        <a class="navbar-item" href="http://huma.io"> Home </a>
        <a class="navbar-item" href="http://huma.io"> Blog </a>
      </div>

    </div>

  </navbar>
</template>


<script>
export default {
  data () {
    return { showNav: false }
  },
  head: {
      htmlAttrs: {
        class: "has-navbar-fixed-top"
      }
  }
};
</script>

<style>
html.has-navbar-fixed-top {
    padding-top: 113px;
}

.huma_logo {
  margin-top: 8px;
  margin-right: 32px;
  margin-bottom: 8px;
  margin-left: 8px;
}
</style>
