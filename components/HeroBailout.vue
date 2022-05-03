<template>
  <section id="bailout" class="hero-bailout">
    <div class="hero-bailout-number">
      <div :class="['hero-bailout-marquee', !isPaused && 'active']">
        <div class="scroll">
          100.000.000.000€
        </div>
        <div class="scroll">
          100.000.000.000€
        </div>
        <div class="scroll">
          100.000.000.000€
        </div>
        <div class="scroll">
          100.000.000.000€
        </div>
      </div>
    </div>
    <div class="hero-bailout-subtitle">
      <div class="container"><slot /></div>
    </div>
  </section>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import gsap from 'gsap' 
import scrollTrigger from 'gsap/ScrollTrigger'

const isPaused = ref(true)

onMounted(() => {
  gsap.registerPlugin(scrollTrigger)
  scrollTrigger.create({
    trigger: '.hero-bailout',
    start: 'top center',
    onToggle () {
      isPaused.value = false
    }
  })
})
</script>

<style lang="scss" scoped>
.hero-bailout {
  background: var(--blue);
  font-family: var(--font-bank);
  color: var(--white);
  height: 100vh;
  display: grid;
  grid-template-rows: 1fr auto;
  align-items: center;
  --move-initial: 0;
  --move-final: -100%;

  &-subtitle {
    font-size: clamp(2.5rem, 5vw, 4rem);
    line-height: 1.2;
    padding: 2rem 0;
  }

  &-number {
    overflow: hidden;
  }

  &-marquee {
    animation: scroll 15s linear infinite;
    animation-play-state: paused;
    transform: translate3d(var(--move-initial), 0, 0);
    display: flex;

    .scroll {
      font-size: clamp(20rem, 35vw, 40rem);
      line-height: 1.2;
      align-self: center;
      transform: translateY(2vw);
      margin-left: 20vw;
    }

    &.active {
      animation-play-state: running;
    }
  }
}

@keyframes scroll {
  0% {
    transform: translate3d(var(--move-initial), 0, 0);
  }

  100% {
    transform: translate3d(var(--move-final), 0, 0);
  }
}
</style>
