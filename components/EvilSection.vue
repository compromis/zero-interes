<template>
  <section class="evil-section">
    <div class="container">
      <div class="evil-grid">
        <div class="evil-heading">
          <h2><slot name="heading" /></h2>
        </div>
        <div class="evil-content">
          <div class="evil-card">
            <slot />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.evil {
  &-section {
    background: var(--white);
    font-family: var(--font-compromis);
    padding: 5rem 0;
  }

  &-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 2rem;
  }

  &-heading {
    color: var(--orange);
    position: relative;

    h2 {
      position: sticky;
      top: 4rem;
      font-size: clamp(2.5rem, 7.5vw, 4rem);
      line-height: 1;
    }
  }

  &-card {
    --spacing: 1.75rem;
    --border: 2px solid var(--black);
    border: var(--border);
    padding: 0 var(--spacing);

    & > * {
      padding: var(--spacing) 0;
    }

    & > *:not(:last-child) {
      border-bottom: var(--border);
    }
  }
}
</style>