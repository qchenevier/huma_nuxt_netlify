<template>
  <div>

    <huma-navbar/>

<!--
      <section class="hero is-medium">
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
      </section> -->

    <div class="container">
      <nuxt/>
    </div>

  </div>
</template>

<script>
import HumaNavbar from '~/components/huma-navbar.vue'

export default {
  components: {
    HumaNavbar,
  }
};
</script>
