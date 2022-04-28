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
    <EvilSection>
      <template #heading>
        Saps tot el que guanyen els bancs i els seus directius?
      </template>
      <EvilDatum>
        <template #number>
          <AnimatedNumber :number="100000" /> milions €
        </template>
        Diners del rescat que no han tornat
      </EvilDatum>
      <EvilDatum>
        <template #number>
          20.000 milions €
        </template>
        Beneficis anuals en 2021
      </EvilDatum>
      <EvilDatum>
        <template #number>
          Salaris directius
        </template>
        <ul class="list-reset mb-3">
          <EvilPerson name="Ana Botín" bank="Santander" salary="12.290.000 €" />
          <EvilPerson name="Josep Oliu" bank="Sabadell" salary="9.730.000 €" />
          <EvilPerson name="Carlos Torrers Vila" bank="BBVA" salary="7.840.000 €" />
          <EvilPerson name="Gonzalo Gortázar" bank="CaixaBank" salary="3.890.000 €" />
          <EvilPerson name="Maria Dolores Dancausa" bank="Bankinter" salary="1.410.000 €" />
        </ul>
        <a href="https://cincodias.elpais.com/cincodias/2022/03/01/companias/1646158931_995561.html" target="_blank" rel="noopener noreferer">
          Tots els salaris
        </a>
      </EvilDatum>
    </EvilSection>
    <EvilSection>
      <template #heading>
        I amb tot açò, què fan per tu?
      </template>
      <EvilDatum>
        <template #number>
          2.940
        </template>
        <template #secondary>
          <span class="text-red">-57%</span>
        </template>
        Oficines tancades de 5.015 que hi havia en 2008.
      </EvilDatum>
      <EvilDatum>
        <template #number>
          Horaris d’atenció reduits
        </template>
        On abans l’atenció era continuada durant tot l’horari, ara és reduïda, i moltes vegades online.
      </EvilDatum>
      <EvilDatum>
        <template #number>
          10.000
        </template>
        Empleats de banca acomiadats des de 2008
      </EvilDatum>
      <EvilDatum>
        <template #number>
          45%
        </template>
        <template #secondary>
          <span class="text-red">-249</span>
        </template>
        dels pobles valencians s’han quedat sense cap oficina bancària
      </EvilDatum>
      <EvilDatum>
        <template #number>
          138.356
        </template>
        valencians i valencianes sense accés a un caixer
      </EvilDatum>
    </EvilSection>
    <EvilSection>
      <template #heading>
        L’abandonament dels pobles per part de la banca
      </template>
      <BankBranches :before="['Oficines 2008', 5105]" :after="['Oficines 2019', 2940]" />
    </EvilSection>
    <HeroGrandma>
      <template #top>
        <div class="line"><span>Volem</span></div>
        <div class="line"><span>una</span><span>banca</span></div>
        <div class="line"><span>pública</span></div>
      </template>
      <template #bottom>
        <div class="line"><span>que</span><span>pense</span></div>
        <div class="line"><span>en</span><span>les</span></div>
        <div class="line"><span>persones</span></div>
      </template>
    </HeroGrandma>
  </main>
</template>
