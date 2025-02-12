<script setup lang="ts">
import { computed } from 'vue'

interface ISite {
  name: string
  url: string
}

const sites = computed(() => {
  return [
    { name: 'Casas Bahia', url: 'https://test.com.br' },
    { name: 'Havan', url: 'https://test.com.br' },
    { name: 'Carrefour', url: 'https://test.com.br' },
    { name: 'Magazine Luiza', url: 'https://test.com.br' },
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
    Queridos amigos e familiares Lorem Ipsum is simply dummy text of the
    printing and typesetting industry. Lorem Ipsum has been the industry's
    standard dummy text ever since the 1500s, when an unknown printer took a
    galley of type and scrambled it to make a type specimen book. It has
    survived not only five centuries, but also the leap into electronic
    typesetting, remai.
  </section>

  <section class="mb-32">
    <div class="title mb-32">Sites</div>
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
      <img src="@/assets/pix.png" height="200px" width="200px" />
    </div>
    <div class="description">
      <p>PIX: 457.850.698-30</p>
      <p>NuBank - Kaique Souza Silva</p>
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
  max-width: 500px
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
