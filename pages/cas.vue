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
        :sentences="[
          'en devolver el dinero del rescate',
          'en atenderte presencialmente',
          'en mantener las oficinas abiertas',
          'en mantener los puestos de trabajo'
        ]"
        wider />
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

<style lang="scss">

</style>
