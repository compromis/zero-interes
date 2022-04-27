<template>
  <section class="hero-grandma">
    <div class="hero-grandma-text">
      <div class="text-orange"><slot name="top" /></div>
      <div><slot name="bottom" /></div>
    </div>
    <img src="../assets/images/granny.jpg" alt="">
  </section>
  <section class="proposal">
    asdfasd
  </section>
</template>

<style lang="scss" scoped>
.hero-grandma {
  background: var(--white);
  height: calc(100vh - 100px);
  position: relative;
  overflow: hidden;
  font-family: var(--font-compromis);

  &-text {
    height: calc(100vh - 100px);
    display: grid;
    grid-template-rows: 1fr auto;
    text-align: center;
    font-size: clamp(2rem, 7vw, 7rem);
    letter-spacing: -0.05em;
    line-height: 1;
    padding-top: 1.5rem;
    padding-bottom: 1.5rem;
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    text-transform: uppercase;
  }

  img {
    z-index: 0;
    height: calc(100vh - 100px);
    object-fit: contain;
    object-position: bottom;
    padding-top: 12vh;
    width: 100%;
  }

  .text-orange {
    color: var(--orange);
  }
}

.proposal {
  background: var(--orange);
  height: 100vh;
}
</style>