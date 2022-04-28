<template>
  <section class="hero-grandma">
      <div class="hero-grandma-text-first text-orange">
        <div class="line"><span>Volem</span></div>
        <div class="line"><span>una</span><span>banca</span></div>
        <div class="line"><span>pública</span></div>
      </div>
      <img src="../assets/images/granny.jpg" alt="">
      <div class="hero-grandma-text-second">
        <div class="line"><span>que</span><span>pense</span></div>
        <div class="line"><span>en</span><span>les</span></div>
        <div class="line"><span>persones</span></div>
      </div>
  </section>
  <section class="proposal">
    asdfasd
  </section>
</template>

<script>
  import gsap from 'gsap' 
  import scrollTrigger from 'gsap/ScrollTrigger'

  export default {
    mounted () {
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
      );

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
      );
    },
  }
</script>

<style lang="scss" scoped>
.hero-grandma {
  background: var(--white);
  max-height: 70vh;
  position: relative;
  overflow: hidden;
  font-family: var(--font-compromis);
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

  span {
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

.proposal {
  background: var(--orange);
  height: 100vh;
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