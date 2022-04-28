<script setup>
import HeroInterest from '@/components/HeroInterest.vue'
import HeroBailout from '@/components/HeroBailout.vue'
import HeroGrandma from '@/components/HeroGrandma.vue'
</script>

<template>
  <main>
    <HeroInterest>
      <ZeroInterest />
    </HeroInterest>
    <HeroBailout>
      Diners que hem pagat per a rescatar als bancs i que tenen 0% interés en tornar.
    </HeroBailout>
    <HeroGrandma>
      <template #top>
        Volem una <br> banca pública
      </template>
      <template #bottom>
        que fique les <br> persones al centre
      </template>
    </HeroGrandma>
  </main>
</template>
