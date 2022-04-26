<script setup>
import BNav from '@compromis/blobby/components/nav/BNav.vue'
import BNavItem from '@compromis/blobby/components/nav/BNavItem.vue'
</script>

<template>
  <div>
    <b-nav no-spacer collapse-at="lg">
      <template #logo-append>
        <nuxt-link to="/">0% d'interés</nuxt-link>
      </template>
      <template #basic-nav>
        <li class="nav-menu-item d-md-none">
          <nuxt-link to="/cas">CAS</nuxt-link>
        </li>
        <li class="nav-menu-item d-none d-md-flex">
          <nuxt-link to="/cas">En castellano</nuxt-link>
        </li>
      </template>
    </b-nav>
    <nuxt-page />
  </div>
</template>

<style lang="scss">
@font-face {
    font-family: 'Gilroy';
    src: url('../assets/fonts/Gilroy-BlackItalic.woff2') format('woff2'),
        url('../assets/fonts/Gilroy-BlackItalic.woff') format('woff'),
        url('../assets/fonts/Gilroy-BlackItalic.ttf') format('truetype');
    font-weight: 900;
    font-style: italic;
    font-display: swap;
}

@font-face {
    font-family: 'Gilroy';
    src: url('../assets/fonts/Gilroy-ExtraBoldItalic.woff2') format('woff2'),
        url('../assets/fonts/Gilroy-ExtraBoldItalic.woff') format('woff'),
        url('../assets/fonts/Gilroy-ExtraBoldItalic.ttf') format('truetype');
    font-weight: bold;
    font-style: italic;
    font-display: swap;
}

@font-face {
    font-family: 'Gilroy';
    src: url('../assets/fonts/Gilroy-SemiBold.woff2') format('woff2'),
        url('../assets/fonts/Gilroy-SemiBold.woff') format('woff'),
        url('../assets/fonts/Gilroy-SemiBold.ttf') format('truetype');
    font-weight: 600;
    font-style: normal;
    font-display: swap;
}
</style>