<template>
  <div class="page-wrapper">
    
    <div class='about'>
      <h2 class="section-headline">привет and welcome</h2>    
      <img class='section-greeting' src='/img/hey.jpg'/>  
    </div>    


   
</div>    

</template>

<script>

export default {
  
}
</script>



<style lang='sass'>

@font-face
  font-family: 'Pangolin'
  font-style: normal
  font-weight: 500
  font-display: swap
  src: url('~assets/fonts/Pangolin.ttf') format('truetype')
.about
  @include flexcolumncenter

.section-greeting
  margin-top: 40px
  width: 90%
  height: auto

p
  font-family: 'Pangolin'
  font-size: 26px
  text-align: justify

</style>
