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
      Dinero que hemos pagado para rescatar a los bancos y que tienen 0% de interés en devolver.
    </HeroBailout>
    <SiteSection>
      <template #heading>
        Mientras ellos se llenan los bolsillos...
      </template>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN1" :to-number="100000" /> millones €
        </template>
        Dinero del rescate que no han devuelto
      </SiteFact>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN2" :to-number="20000" /> millones €
        </template>
        Beneficios anuales en 2021
      </SiteFact>
      <SiteFact>
        <template #heading>
          Salarios directivos
        </template>
        <ul class="list-reset mb-3">
          <BankerPerson name="Mª Dolores Dancausa" bank="Bankinter" :salary="1410000" id="P5" />
          <BankerPerson name="Gonzalo Gortázar" bank="CaixaBank" :salary="3890000" id="P4" />
          <BankerPerson name="Carlos Torrers Vila" bank="BBVA" :salary="7840000" id="P3" />
          <BankerPerson name="Josep Oliu" bank="Sabadell" :salary="9730000" id="P2" />
          <BankerPerson name="Ana Botín" bank="Santander" :salary="12290000" id="P1" />
        </ul>
        <a href="https://cincodias.elpais.com/cincodias/2022/03/01/companias/1646158931_995561.html" target="_blank" rel="noopener noreferer">
          Todos los salarios
        </a>
      </SiteFact>
    </SiteSection>
    <SiteSection>
      <template #heading>
        ... a ti te dan la espalda
      </template>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN3" :to-number="2940" />
        </template>
        <template #secondary>
          <span class="text-red"><AnimatedNumber id="AN31" :to-number="-57" />%</span>
        </template>
        Oficinas cerradas de 5.104 que había en 2008.
      </SiteFact>
      <SiteFact>
        <template #heading>
          Horarios de atención reducidos
        </template>
        Donde antes la atención era continua durante todo el horario, ahora es reducida, y muchas veces online.
      </SiteFact>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN4" :to-number="100000" />
        </template>
        Empleados de banca despedidos desde 2008
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
        de los pueblos valencianos se han quedado sin ninguna oficina bancaria
      </SiteFact>
      <SiteFact>
        <template #heading>
          <AnimatedNumber id="AN6" :to-number="138356" />
        </template>
        valencianos y valencianas sin acceso a un cajero
      </SiteFact>
    </SiteSection>
    <SiteSection>
      <template #heading>
        Pueblos abandonados por la banca
      </template>
      <BankBranches :before="['Oficinas 2008', 5105]" :after="['Oficinas 2019', 2164]" />
      <SiteFact>
        <template #heading>
          Pueblos sin ninguna oficina
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
        <div class="line"><span>Queremos</span></div>
        <div class="line"><span>una</span><span>banca</span></div>
        <div class="line"><span>pública</span></div>
      </template>
      <template #bottom>
        <div class="line"><span>que</span><span>piense</span></div>
        <div class="line"><span>en</span><span>las</span></div>
        <div class="line"><span>personas</span></div>
      </template>
    </HeroGrandma>
    <SiteSection inverted>
      <template #heading>
        ¿Qué proponemos?
      </template>
      <SiteFact>
        <template #heading>
          Una banca pública
        </template>
        <p>
          Si los bancos privados solo quieren ganar y maltratar a sus clientes,
          haremos una banca pública para que la ciudadanía tenga un lugar donde
          depositar sus ahorros. Queremos que el Institut Valencià de Finances (IVF)
          sea la Banca Pública Valenciana que queremos, con oficinas en los pueblos.
        </p>
      </SiteFact>
      <SiteFact>
        <template #heading>
          Que los bancos estén obligados a atender presencialmente
        </template>
        <p>
          Impulsamos propuestas para obligar a los bancos a prestar unos servicios mínimos como
          la atención presencial, y a tener presencia en todos los municipios para dar
          alcance a la ciudadanía.
        </p>
      </SiteFact>
      <SiteFact>
        <template #heading>
          Proteger los derechos de la ciudadanía ante los bancos
        </template>
        <p>
          Queremos cambiar la ley de consumo para que los derechos de los clientes de los bancos
          estén protegidos, y la banca no pueda abusar de ellos.
        </p>
      </SiteFact>
    </SiteSection>
  </main>
</template>
