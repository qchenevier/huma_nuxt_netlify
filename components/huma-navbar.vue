<template>
  <navbar class="navbar container is-fixed-top">

    <div class="navbar-brand">

      <a href="/">
        <figure
          :class="['image', imgClass]"
          :style="humaLogoStyle"
          href="/"
        >
          <img src="~/assets/huma_logo.svg"/>
        </figure>
      </a>

      <div
        class="navbar-burger"
        @click="showNav = !showNav"
        :class="{'is-active': showNav}"
        :style="{'height': burgerSize + 'px'}"
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
        <a class="navbar-item" href="/"> Home </a>
      </div>

    </div>

  </navbar>
</template>


<script>
var logoSize = 96 // choose a value in this list (available in bulma classes): 16, 24, 32, 48, 64, 96, 128

var marginSize = logoSize / 12
var navbarSize = logoSize + 2 * marginSize

export default {
  data () {
    return {
      showNav: false,
      logoSize: logoSize,
      marginSize: marginSize,
      burgerSize: navbarSize,
      imgClass: 'is-' + logoSize + 'x' + logoSize,
      humaLogoStyle: {
        'margin-top': marginSize + 'px',
        'margin-right': 4 * marginSize + 'px',
        'margin-bottom': marginSize + 'px',
        'margin-left': marginSize + 'px'
      }
    }
  },
  head: {
      htmlAttrs: {
        style: 'padding-top: ' + (navbarSize + 1) + 'px'
      }
  }
};
</script>

<style>
</style>
