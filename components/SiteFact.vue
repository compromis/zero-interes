<template>
  <article class="evil-datum">
    <h3 class="evil-datum-heading">
      <slot name="heading" />
      <div class="evil-datum-secondary" v-if="$slots.secondary">
        <slot name="secondary" />
      </div>
    </h3>
    <div class="evil-datum-content">
      <slot />
    </div>
  </article>
</template>

<style lang="scss" scoped>
.evil-datum {
  h3 {
    font-size: 2rem;
  }

  &-heading {
    display: flex;
  }

  &-secondary {
    margin-left: auto;
    padding-left: 1rem;
  }

  &-content {
    font-weight: 400;
    font-size: 1.25rem;
    line-height: 1.1;
  }

  :deep(a) {
    color: var(--black);
    text-decoration: underline;

    &:hover {
      color: var(--orange);
    }
  }
}
</style>