<template>
  <section class="hero-grandma">
    <div class="hero-grandma-text-first text-orange">
      <slot name="top" />
    </div>
    <img :src="grannyImage" alt="">
    <div class="hero-grandma-text-second">
      <slot name="bottom" />
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap' 
import scrollTrigger from 'gsap/ScrollTrigger'
import grannyImage from '../assets/images/granny.jpg'

onMounted(() => {
  gsap.registerPlugin(scrollTrigger)
  gsap.from('.hero-grandma-text-first span', 
    {
      scrollTrigger: {
        trigger: '.hero-grandma-text-first',
        start: 'top 70%'
      },
      y: 125,
      duration: 1.5,
      stagger: 0.15,
      ease: 'Power4.easeOut'
    }
  )

  gsap.from('.hero-grandma-text-second span',
    {
      scrollTrigger: {
        trigger: '.hero-grandma-text-second',
        start: 'top 90%'
      },
      y: 125,
      duration: 1.5,
      stagger: 0.15,
      ease: 'Power4.easeOut',
      delay: 1
    }
  )
})
</script>

<style lang="scss" scoped>
.hero-grandma {
  background: var(--white);
  max-height: 70vh;
  position: relative;
  overflow: hidden;
  font-family: var(--font-compromis);
  font-weight: 900;
  display: grid;
  grid-template-columns: 1fr 25vw 1fr;
  align-items: center;
  text-align: center;
  font-size: clamp(2.75rem, 4.5vw, 6rem);
  letter-spacing: -0.05em;
  line-height: 1;
  text-transform: uppercase;

  &-text-first {
    text-align: left;
    padding-left: 3vw;
  }

  &-text-second {
    text-align: right;
    padding-right: 3vw;
  }

  :deep(.line) {
    overflow: hidden;
  }

  :deep(span) {
    display: inline-block;
    padding: 0 .1em;
  }

  img {
    z-index: 0;
    object-fit: contain;
    object-position: bottom;
    padding-top: 2vh;
    width: 100%;
    height: 100%;
  }

  .text-orange {
    color: var(--orange);
  }
}

@media (max-width: 700px) {
  .hero-grandma {
    grid-template-columns: 1fr;

    &-text {
      &-first, &-second {
        z-index: 10;
        text-align: center;
        position: absolute;
        left: 0;
        right: 0;
      }

      &-first {
        top: 1rem;
      }

      &-second {
        bottom: 1rem;
      }
    }

    img {
      padding-top: 15vh;
    }
  }
}
</style>
