<template>
  <section class="hero">
    <div class="image">
      <slot />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero {
  background-image: linear-gradient(to right, #bdb1b1 0%, #bdb1b1 50%, #e3dfde 50%, #e3dfde 100%);
}

.image {
  height: 100vh;
  min-height: 40vw;
  display: flex;
  max-width: 2000px;
  margin: 0 auto;
  font-family: var(--font-bank);

  :deep(.text) {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 700px) {
  .image {
    height: 140vw;
  }
}
</style>