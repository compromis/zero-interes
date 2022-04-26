<template>
  <div class="hero-grandma">
    <div class="hero-grandma-text">
      <div style="color: #EC6830">Volem una  <br> banca pública</div>
      <div>que fique les <br> persones al centre</div>
    </div>
    <img src="../assets/images/granny.jpg" alt="">
  </div>
  <div style="height: 100vh; background: orange;">
    asdfasd
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style lang="scss" scoped>
.hero-grandma {
  background: white;
  height: calc(100vh - 100px);
  position: relative;
  overflow: hidden;
  font-family: 'Fixture', sans-serif;

  &-text {
    height: calc(100vh - 100px);
    display: grid;
    grid-template-rows: 1fr auto;
    text-align: center;
    font-size: clamp(2.5rem, 7.5vw, 8rem);
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
}
</style>