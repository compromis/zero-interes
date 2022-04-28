<template>
  <section class="hero-grandma">
    <div class="hero-grandma-text">
      <div class="hero-grandma-text-first" style="color: #EC6830">
        <div class="line"><span>Volem</span><span>una</span></div>
        <div class="line"><span>banca</span><span>pública</span></div>
      </div>
      <div class="hero-grandma-text-second">
        <div class="line"><span>que</span><span>fique</span><span>les</span></div>
        <div class="line"><span>persones</span><span>al</span><span>centre</span></div>
      </div>
    </div>
    <img src="../assets/images/granny.jpg" alt="">
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
          ease: 'Power4.easeOut'
        }
      );
    },
  }
</script>

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

    :deep(.line) {
      overflow: hidden;
    }

    span {
      display: inline-block;
      padding: 0 .1em;
    }
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