<template>
  <div class="engbar">
    <ul class="navlist">
      <li class="nav-link"><NuxtLink to='/eng/articles'>артикли</NuxtLink></li>
      <li class="nav-link"><NuxtLink to='/eng/preps'>предлоги</NuxtLink></li>
      <li class="nav-link"><NuxtLink to='/eng/pronouns'>местоимения</NuxtLink></li>
      <li class="nav-link"><NuxtLink to='/eng/comics'>комиксы</NuxtLink></li>
      <li class="nav-link"><NuxtLink to='/eng/verbs'>глаголы</NuxtLink></li>
      </ul>
 </div>

</template>

<style lang='sass' scoped>
@font-face
    font-family: 'Pangolin'
    font-style: normal
    font-weight: 500
    font-display: swap
    src: url('~assets/fonts/Pangolin.ttf') format('truetype')

.engbar
  width: 200px
  height: 350px
  z-index: 1001
  background: $egg
  display: flex
  position: absolute
  top: 0
  display: none
  margin-top: 70px
  ul
    @include flexcolumncenter
    width: 100%
    list-style: none
    padding-left: 0
    li
      text-decoration: none
      height: 55px
      letter-spacing: 3px
      font-size: 20px
      font-weight: 500
      color: $transblack
      margin-right: 10px
      font-family: 'Pangolin'

.nav-link .nuxt-link-exact-active
  color: $cherry

a, .nuxt-link, .nuxt-link-active
  text-decoration: none
  color: $transblack


@media(max-width: 500px)
   
  
</style>

<script>
  export default{

  }
</script>