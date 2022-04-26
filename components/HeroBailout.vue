<template>
  <div class="hero-bailout">
    <ClientOnly>
      <MarqueeText class="hero-bailout-marquee" :duration="40" :repeat="2">
        <div class="scroll">
          100.000.000.000€
        </div>
      </MarqueeText>
    </ClientOnly>
    <div class="hero-bailout-subtitle">Diners que hem pagat per a rescatar als bancs i que tenen 0% interés en tornar.</div>
  </div>
</template>

<style lang="scss" scoped>
.hero-bailout {
  background: #00A7DD;
  font-family: 'Gilroy', sans-serif;
  color: white;
  height: 100vh;
  display: grid;
  grid-template-rows: 1fr auto;
  align-items: center;

  &-subtitle {
    font-size: clamp(2.5rem, 5vw, 4rem);
    line-height: 1.2;
    max-width: calc(1296px + 1rem);
    margin: 0 auto;
    padding: 2rem 1rem;
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
