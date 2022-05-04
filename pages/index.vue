<template>
  <main>
    <HeroInterest>
      <ZeroInterest />
    </HeroInterest>
    <HeroBailout>
      Diners que hem pagat per a rescatar als bancs i que tenen 0% interés en tornar.
    </HeroBailout>
    <SiteSection>
      <template #heading>
        Mentre ells s'omplin les butxaques...
      </template>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN1" :to-number="100000" /> milions €
        </template>
        Diners del rescat que no han tornat
      </SiteFact>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN2" :to-number="20000" /> milions €
        </template>
        Beneficis anuals en 2021
      </SiteFact>
      <SiteFact>
        <template #heading>
          Salaris directius
        </template>
        <ul class="list-reset mb-3">
          <BankerPerson name="Mª Dolores Dancausa" bank="Bankinter" :salary="1410000" id="P5" />
          <BankerPerson name="Gonzalo Gortázar" bank="CaixaBank" :salary="3890000" id="P4" />
          <BankerPerson name="Carlos Torrers Vila" bank="BBVA" :salary="7840000" id="P3" />
          <BankerPerson name="Josep Oliu" bank="Sabadell" :salary="9730000" id="P2" />
          <BankerPerson name="Ana Botín" bank="Santander" :salary="12290000" id="P1" />
        </ul>
        <a href="https://cincodias.elpais.com/cincodias/2022/03/01/companias/1646158931_995561.html" target="_blank" rel="noopener noreferer">
          Tots els salaris
        </a>
      </SiteFact>
    </SiteSection>
    <SiteSection>
      <template #heading>
        ... a tu et donen l'esquena
      </template>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN3" :to-number="2940" />
        </template>
        <template #secondary>
          <span class="text-red"><AnimatedNumber id="AN31" :to-number="-57" />%</span>
        </template>
        Oficines tancades de 5.104 que hi havia en 2008.
      </SiteFact>
      <SiteFact>
        <template #heading>
          Horaris d’atenció reduits
        </template>
        On abans l’atenció era continuada durant tot l’horari, ara és reduïda, i moltes vegades online.
      </SiteFact>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN4" :to-number="100000" />
        </template>
        Empleats de banca acomiadats des de 2008
      </SiteFact>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN5" :to-number="45" />%
        </template>
        <template #secondary>
          <span class="text-red">
            <AnimatedNumber id="AN51" :to-number="-249" />
          </span>
        </template>
        dels pobles valencians s’han quedat sense cap oficina bancària
      </SiteFact>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN6" :to-number="138356" />
        </template>
        valencians i valencianes sense accés a un caixer
      </SiteFact>
    </SiteSection>
    <SiteSection>
      <template #heading>
        Pobles abandonats per la banca
      </template>
      <BankBranches :before="['Oficines 2008', 5105]" :after="['Oficines 2019', 2940]" />
      <SiteFact>
        <template #heading>
          Pobles sense cap oficina
        </template>
        <BranchlessTowns
          :data="[
            ['Castelló', 89, 46],
            ['València', 103, 163],
            ['Alacant', 57, 84]
          ]" />
      </SiteFact>
    </SiteSection>
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
    <SiteSection inverted>
      <template #heading>
        Què proposem?
      </template>
      <SiteFact>
        <template #heading>
          Una banca pública
        </template>
        <p>
          Si els bancs privats només volen guanyar i maltractar als seus clients,
          farem una banca pública perquè la ciutadania tinga un lloc on dipositar
          els seus estalvis. Volem que l’Institut Valencià de Finances (IVF)
          siga la Banca Pública Valenciana que volem, amb oficines en els pobles
        </p>
      </SiteFact>
      <SiteFact>
        <template #heading>
          Que els bancs estiguen obligats a atendre presencialment
        </template>
        <p>
          Impulsem propostes per obligar als bancs a prestar uns serveis mínims com
          l’atenció presencial, i a tindre presència en tots els municipis per donar
          abast a la ciutadania.
        </p>
      </SiteFact>
      <SiteFact>
        <template #heading>
          Protegir els drets de la ciutadania davant els bancs
        </template>
        <p>
          Volem canviar la llei de consum perquè els drets dels clients dels bancs
          estiguen protegits, i la banca no puga abusar d’ells.
        </p>
      </SiteFact>
    </SiteSection>
  </main>
</template>
