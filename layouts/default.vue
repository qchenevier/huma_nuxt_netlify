<template>
  <div>
    <nav class="navbar">

      <div class="navbar-brand">

        <a href="http://huma.io">
          <figure class="image is-96x96 huma_logo" href="http://huma.io" style="margin:8px">
            <img src="~/assets/huma_logo.svg"/>
          </figure>
        </a>

        <div class="navbar-burger" @click="showNav = !showNav" :class="{ 'is-active': showNav }"  style="height: 104px;">
          <span></span>
          <span></span>
          <span></span>
        </div>

      </div>

      <div class="navbar-menu" :class="{ 'is-active': showNav }">

        <div class="navbar-start">
          <a class="navbar-item" href="http://huma.io">
            Home
          </a>
          <a class="navbar-item" href="http://huma.io">
            Blog
          </a>
        </div>

      </div>

    </nav>

    <section class="hero">
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
    </section>

    <nuxt/>

  </div>
</template>

<script>
export default {
  data() {
    return { showNav: false }
  }
};
</script>

<style>
</style>
