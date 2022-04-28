<template>
  <li class="evil-person">
    <span class="name">{{ name }}</span>
    <span class="bank">{{ bank }}</span>
    <span class="spacer" />
    <span class="salary">
      <AnimatedNumber :id="id" :to-number="salary" currency />
    <span class="per-annum">/any</span></span>
  </li>
</template>

<script setup>
defineProps({
  id: {
    type: String,
    required: true
  },
  name: {
    type: String,
    required: true
  },
  bank: {
    type: String,
    required: true
  },
  salary: {
    type: String,
    required: true
  }
})
</script>

<style lang="scss" scoped>
.evil-person {
  display: flex;
  align-items: baseline;
  gap: .5rem;
  padding: .5rem 0;

  .bank {
    font-size: 1rem;
  }

  .spacer {
    flex-grow: 1;
    border-bottom: 1px dotted var(--black);
  }

  .per-annum {
    font-size: 1rem;
  }
}
</style>