<template>
  <div>
    <Header />
    <Nuxt />
  </div>
</template>

<style lang="sass">
@font-face
    font-family: 'Oswaldd'
    font-weight: 600
    src: url('~assets/Oswaldd.ttf')
html
  font-family: 'Source Sans Pro'
  font-size: 16px

*,
*::before,
*::after 
  box-sizing: border-box
  margin: 0

.section-headline
  color: rgba(135, 12, 55, .8)
  font-family: Pangolin
  font-size: 32px
  text-align: center
  font-weight: 600
  display: flex
  align-items: center
  justify-content: center
  margin-bottom: 30px

.page-wrapper
  max-width: 100%
  margin: 0
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

.rare
  letter-spacing: 1rem
h2
  font-family: 'Oswaldd'
  color: rgba(135, 12, 55, 0.8)
@media(max-width:500px)
  .section-headline
    font-size: 25px

</style>

<script>
  import Header from '@/components/Header'
  export default {
  
}
</script>