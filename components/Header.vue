<template>
  <div class='header'>
    <div class="navpannel">       
        
        <div class="navbar">
          <ul class="navlist">
            <li class="nav-link"><NuxtLink to='/'>домой</NuxtLink></li>
            <li class="nav-link"><NuxtLink to='/rus'>русский</NuxtLink></li>
            <li class="nav-link" @click='processClick()'>
              <NuxtLink to='/eng'>английский</NuxtLink>
              <Engbar />
            </li>
          </ul>
        </div>
      </div>
    
 </div>
</template>

<style lang='sass' scoped>
@font-face
  font-family: 'Rubik'
  font-style: normal
  font-weight: 500
  font-display: swap
  src: url('~assets/fonts/Rubik.ttf') format('truetype')


.header
  width: 100%
  height: 70px
  display: flex
  flex-direction: column
  background: $egg
  margin-bottom: 50px

.navpannel
  height: 100%
  width: 100%
  padding: 0 1.5rem 0 1.5rem
  display: flex
  justify-content: space-between
  align-items: center



.navbar
  max-width: 350px
  justify-content: space-around


.navlist
  display: flex
  align-items: center
  justify-content: space-between
  flex-direction: row
  list-style: none
  padding-left: 0
  li
    display: flex
    flex-direction: column

.nav-link a
  text-decoration: none
  font-family: Rubik
  letter-spacing: 3px
  font-size: 20px
  font-weight: 500
  color: $transblack
  margin-right: 10px


// .nuxt-link, .nuxt-link-active
//   text-decoration: none
//   color: black

.nav-link .nuxt-link-exact-active
  color: $cherry

@media(max-width: 800px)
  .nav-link
    margin-right: 7px

@media(max-width: 500px)
  .navbar
    ul
      flex-direction: column 
   
  .nav-link
    a
      font-size: 17px    
  
</style>
<script>
  import Engbar from '@/components/Engbar'
  export default{
    methods:{
      processClick(){        
        let engBar = document.querySelector('.engbar')       
        if (engBar.style.display == 'flex'){
          engBar.style.display = 'none'
        }
        else{
          engBar.style.display = 'flex'
        }
      }
      
    }
  }
</script>