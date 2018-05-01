<template>
  <div>
    <nav class="navbar container">

      <div class="navbar-brand">

        <a href="http://huma.io">
          <figure class="image is-96x96 huma_logo" href="http://huma.io">
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

    <div class="container">
      <nuxt/>
    </div>

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
.huma_logo {
  margin-top: 8px;
  margin-right: 32px;
  margin-bottom: 8px;
  margin-left: 8px;
}
</style>
