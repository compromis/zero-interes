<script setup>
import HeroInterest from '@/components/HeroInterest.vue'
import HeroBailout from '@/components/HeroBailout.vue'
</script>

<template>
  <main>
    <HeroInterest>
      <ZeroInterest
        cta="Me interesa"
        interest="de interés"
        :sentences="['a', 'b', 'c', 'd']" />
    </HeroInterest>
    <HeroBailout />
  </main>
</template>

<style lang="scss">

</style>
