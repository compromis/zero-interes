<template>
  <section :class="['section', { inverted }]">
    <div class="container">
      <div class="section-grid">
        <div class="section-heading">
          <h2><slot name="heading" /></h2>
        </div>
        <div class="section-content">
          <div class="section-card">
            <slot />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps({
  inverted: {
    type: Boolean,
    default: false
  }
})
</script>

<style lang="scss">
.section {
  background: var(--white);
  font-family: var(--font-compromis);
  padding: 5rem 0;

  &-grid {
    display: grid;
    grid-template-columns: 1fr minmax(580px, 1fr);
    grid-gap: 2rem;
  }

  &-heading {
    color: var(--orange);
    position: relative;
    hyphens: auto;

    h2 {
      position: sticky;
      top: 6rem;
      font-size: clamp(2.5rem, 7.5vw, 3.75rem);
      line-height: 1;
    }
  }

  &-card {
    --spacing: 1.75rem;
    --border: 2px solid currentColor;
    border: var(--border);
    padding: 0 var(--spacing);

    & > * {
      padding: var(--spacing) 0;
    }

    & > *:not(:last-child) {
      border-bottom: var(--border);
    }
  }

  &.inverted {
    background: var(--orange);
    color: var(--white);

    .section-heading {
      color: var(--white);
    }
  }
}

@media (max-width: 1300px) {
  .section-grid {
    grid-template-columns: 1fr;
  }

  .section-heading {
    hyphens: none;
  }
}
</style>