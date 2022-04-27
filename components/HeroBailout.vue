<template>
  <section id="bailout" class="hero-bailout">
    <ClientOnly>
      <MarqueeText class="hero-bailout-marquee" :duration="40" :repeat="2">
        <div class="scroll">
          100.000.000.000€
        </div>
      </MarqueeText>
    </ClientOnly>
    <div class="hero-bailout-subtitle">
      <div class="container"><slot /></div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero-bailout {
  background: var(--blue);
  font-family: var(--font-bank);
  color: var(--white);
  height: 100vh;
  display: grid;
  grid-template-rows: 1fr auto;
  align-items: center;

  &-subtitle {
    font-size: clamp(2.5rem, 5vw, 4rem);
    line-height: 1.2;
    padding: 2rem 0;
  }
}
.scroll {
  font-size: clamp(20rem, 35vw, 40rem);
  margin-right: 15vw;
  line-height: 1.2;
  align-self: center;
  transform: translateY(2vw);
}
</style>
