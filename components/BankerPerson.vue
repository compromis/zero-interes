<template>
  <li class="banker-person">
    <span class="name">{{ name }} <span class="bank">{{ bank }}</span></span>
    <span class="spacer" />
    <span class="salary">
      <AnimatedNumber :id="id" :to-number="salary" currency />
      <span class="per-annum">/any</span>
    </span>
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
    type: Number,
    required: true
  }
})
</script>

<style lang="scss" scoped>
.banker-person {
  display: flex;
  align-items: baseline;
  gap: .5rem;
  padding: .5rem 0;

  .bank {
    font-size: 1rem;
    color: var(--text-muted);
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