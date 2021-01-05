<template>
<div class="page-wrapper">
	<div class="comic-card" v-for="comic in comics">
		<img class="comic-image" :src="`/img/nat/${comic.alt}.jpg`" :alt="`${comic.alt}`"/>
		<div class='comic-text'>
			<h3>заметки</h3>
			<!-- <div class='new-words' v-for="word in comic.words"> -->
			<div class="new-words">	
				<vue-typer :text="`${comic.words}`"></vue-typer>

			</div>	
		</div>
	</div>
</div>
</template>

<script>
	export default{
		data(){
			return{
				comics: [
					{alt: 'bread', words:'a toaster - тостер, \n a toast - тост, \n to talk to - говорить с,\n "Не разговаривай со мной..."'},
					{alt: 'dog', words: 'a dog - собака,\n a pug - мопс,\n to stink - вонять,\n "Собака, ты воняешь."'},
					{alt: 'wash', words: 'clean - чистый,\n dirty - грязный,\n to wash - мыть\n, "Помой эту собаку!"'},
					{alt: 'banana', words: 'forget - забывать,\n forgot - забыл,\n about - про,\n "Ты забыл про меня!"'},
					{alt: 'lemon', words: 'pretty - довольно, достаточно,\n good - хороший,\n yellow - желтый,\n a smile - улыбка,\n "Лимоны довольно хорошие"'},
					{alt: 'otter', words: 'baby - ребенок, детеныш\n, otter - выдра,\n cute - милый,\n the cutest - самый милый,\n animal - животное,\n ever - вообще,\n "Детеныш выдры самое милое животное"'},
					{alt: 'cactus', words: 'something - что-то,\n wrong - не так,\n with - с,\n guys - ребята,\n "Что-то не так с моим кактусом, ребята"'},

 
				]
			}
		}
	}
</script>

<style lang="sass" scoped>
@font-face
  font-family: 'Caveat'
  font-style: normal
  font-weight: 500
  font-display: swap
  src: url('~assets/fonts/Caveat.ttf') format('truetype')
.comic-card
  margin-top: 30px
  width: 80%
  display: flex
  flex-direction: row
  justify-content: space-between
  max-height: 600px
  
.comic-image
  width: 65%
 
.comic-text
  width: 30%
  text-align: center
  background-image: url('/img/nat/paper.webp')
  background-size: cover
  padding: 15px 0 20px 0
  h3
    color: $darkcherry
    letter-spacing: 3px
.new-words
  width: 100%
  margin-top: 20px
  font-family: 'Caveat'
  font-size: 30px

@media(max-width: 500px)
  .comic-card
    width: 95%
    @include flexcolumncenter
    img
      border: none
    .comic-text, img
      width: 80%
      min-height: 40px
      .new-words
        font-size: 20px

</style>