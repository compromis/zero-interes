<script setup>
import BNav from '@compromis/blobby/components/nav/BNav.vue'
import BNavItem from '@compromis/blobby/components/nav/BNavItem.vue'
import BFooter from '@compromis/blobby/components/footer/BFooter.vue'

const route = useRoute()
</script>

<template>
  <div>
    <b-nav no-spacer collapse-at="lg">
      <template #logo-append>
        <nuxt-link to="/">0% d'interés</nuxt-link>
      </template>
      <template #basic-nav>
        <li class="nav-menu-item d-md-none">
          <nuxt-link to="/" v-if="route.name === 'cas'">VAL</nuxt-link>
          <nuxt-link to="/cas" v-else>CAS</nuxt-link>
        </li>
        <li class="nav-menu-item d-none d-md-flex">
          <nuxt-link to="/" v-if="route.name === 'cas'">En valencià</nuxt-link>
          <nuxt-link to="/cas" v-else>En castellano</nuxt-link>
        </li>
      </template>
    </b-nav>
    <nuxt-page />
    <div class="footer-wrapper">
      <div class="container">
        <b-footer variant="white" />
      </div>
    </div>
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

@font-face {
    font-family: 'Fixture';
    src: url('../assets/fonts/Fixture-ExpandedBlack.woff2') format('woff2'),
        url('../assets/fonts/Fixture-ExpandedBlack.woff') format('woff'),
        url('../assets/fonts/Fixture-ExpandedBlack.ttf') format('truetype');
    font-weight: 900;
    font-style: normal;
    font-display: swap;
}

:root {
  --white: #fff;
  --blue: #00A7DD;
  --yellow: #f5c53e;
  --orange: #ff5924;
  --black: #222;
  --font-bank: 'Gilroy', sans-serif;
  --font-compromis: 'Fixture', sans-serif;
}

.footer-wrapper {
  background: var(--orange);
  color: white;
}
</style>