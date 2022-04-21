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
