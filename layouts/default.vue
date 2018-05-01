<template>
  <div>
    <nav class="navbar">

      <div class="navbar-brand">
        <a href="http://huma.io">
          <figure class="image is-96x96" href="http://huma.io" style="margin:8px">
            <img src="~/assets/huma_logo.svg" height=1/>
          </figure>
        </a>

        <!-- <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a> -->

      </div>

      <div class="navbar-menu is-active">

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
    <nuxt/>
  </div>
</template>
