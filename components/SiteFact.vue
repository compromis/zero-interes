<template>
  <article class="site-fact">
    <h3 class="site-fact-heading">
      <slot name="heading" />
      <div class="site-fact-secondary" v-if="$slots.secondary">
        <slot name="secondary" />
      </div>
    </h3>
    <div class="site-fact-content">
      <slot />
    </div>
  </article>
</template>

<style lang="scss" scoped>
.site-fact {
  h3 {
    font-size: calc(1.25rem + .6vw);
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
    font-size: calc(1rem + .2vw);
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