<script setup lang="ts">
import { computed } from 'vue'

interface ISite {
  name: string
  url: string
}

const sites = computed(() => {
  return [
    { name: 'Mercado Livre', url: 'https://www.mercadolivre.com.br/presentes/kaique-e-franciane-3m0kv' },
    { name: 'Magazine Luiza', url: 'https://www.finalfeliz.de/kaique-franciane-casamento' },
    { name: 'Casas Bahia', url: 'https://listas.casasbahia.com.br/kaiqueefranciane052025' },
  ] as Array<ISite>
})

const openSite = (site: ISite) => {
  const a = document.createElement('a')
  a.href = site.url
  a.target = '_blank'
  a.click()
}
</script>

<template>
  <header>
    <img
      alt="Casamento data"
      class="logo mb-32"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />
    <div class="title mb-32">Kaique & Franciane</div>
  </header>

  <section class="description mb-32">
    <b style="font-weight: bold !important;">Olá, queridos amigos e familiares!</b>
    <br>
    <br>
    <p>
      Estamos muito feliz em poder compartilhar este momento tão especial com cada um de vocês. 
      Para nós, é uma grande alegria saber que vocês estarão ao nosso lado nessa nova jornada!
    </p>
    <p>
      Muitos de vocês nos pediram sugestões para nos presentear, e ficamos imensamente 
      gratos por isso. Esta lista de presentes foi criada com todo o cuidado, com itens que 
      acreditamos serem úteis para o início da nossa vida juntos. No entanto, gostaríamos 
      que soubessem que ela é apenas uma orientação. Fiquem à vontade para se inspirar nela.
    </p>
    <p>
      Agradecemos profundamente por todo apoio e por estarem ao nosso lado nessa etapa tão especial.
    </p>
    <br>
    <p>Com carinho,</p>
    <p>Fran & Kaique.</p>
  </section>

  <section class="mb-32">
    <div class="title mb-32">Listas</div>
    <button
      v-for="(site, i) in sites"
      :key="`site-${i}`"
      class="button"
      @click="openSite(site)"
    >
      {{ site.name }}
    </button>
  </section>

  <section>
    <div class="title mb-32">Pix</div>
    <div class="pix-container mb-32">
      <img src="@/assets/qrcode.png" height="200px" width="200px" />
    </div>
    <div class="description">
      <p>PIX: kaiquesouzasilva11@gmail.com</p>
      <p>C6 Bank - Kaique Souza Silva</p>
    </div>
  </section>

  <img class="footer" src="@/assets/footer.png" width="100%" />
</template>

<style scoped lang="sass">
header
  line-height: 1.5
  max-height: 100vh

.logo
  display: block
  margin: auto

.mb-32
  margin-bottom: 32px

.title
  font-family: Baskervville !important
  color: var(--color-purple) !important
  font-size: 38px
  text-align: center

.description
  font-size: 14px
  text-align: center
  max-width: 450px
  margin-left: auto
  margin-right: auto

.button
  background: var(--color-purple-light)
  border: 0px
  height: 48px
  border-radius: 8px
  display: block
  width: 100%
  max-width: 450px
  margin: auto
  margin-bottom: 24px
  color: white
  font-weight: bold
  font-size: 15px
  font-family: 'Open Sans' !important
  cursor: pointer
  &:hover
    background: var(--color-purple)

.pix-container
  background: white
  width: 200px
  height: 200px
  margin: 0 auto
  margin-bottom: 32px

@media screen and (max-width: 500px)
  .footer
    position: relative
    width: 100vw
    margin-left: -2rem
    margin-bottom: -2.2rem
</style>
