<template>
  <div class="page-wrapper">

    <section id='cases'>
    	<h2 class='section-headline'>Падежные окончания</h2>
    	<grid />
    </section>
  
  </div>
</template>

<script>

import Grid from '@/components/Grid'
export default {
Components: {
	grid:Grid
}

}
</script>


<style scoped lang="sass">

#cases
	width: 80%
	display: flex
	flex-direction: column

</style>