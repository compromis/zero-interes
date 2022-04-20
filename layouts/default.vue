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
        <ul aria-title="Menú principal" class="nav-menu nav-menu-abridged">
          <li class="nav-menu-item">
            <nuxt-link to="/cas">En castellano</nuxt-link>
          </li>
        </ul>
      </template>
    </b-nav>
    <nuxt-page />
  </div>
</template>
