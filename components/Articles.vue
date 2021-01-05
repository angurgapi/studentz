<template>
	<div class='app'>
		<h2 class="section-headline">выберите правильный вариант</h2>
		<div class="articles-test" v-for="opt in options">
			<h3 class="question-headline">{{ opt.title }}</h3>
			<img class="question-image" :src="`/img/articles/${opt.alt}.jpg`" :alt="`${opt.alt}`"/>
			<div class='options'>
				<div class="opt-wrapper" v-for="choice in opt.choices" @click='processTry()'>
					<h4 class='opt'>{{ choice }}</h4>
				</div>	
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		data(){
			return{
				options:[
					{title: 'Это моя семья', alt: 'family', choices: ['This is the my family', 'This is my family', 'This is a family']},
					{title: 'Мне нужно полотенце', alt: 'wet', choices: ['I need towel', 'I need a towel', 'I need the potatoes']},
					{title: 'Машина сломалась!', alt: 'car', choices: ['The car is broken', 'Car is broken', 'A car is broken']},
					{title: 'У нас два мороженых', alt: 'ice-cream', choices: ["We've got a two ice-creams", "We've got an ice-creams", "We've got two ice-creams"]},	

				],
				correctAnswers:[
				'This is my family', 'I need a towel', 'The car is broken', "We've got two ice-creams"
				]
			}
		},

	
	methods: {
		processTry(){
			let parent = event.target.closest('.opt-wrapper')
			if(this.correctAnswers.indexOf(event.target.innerHTML)>-1){
				parent.classList.add('true-opt')
				let audio = new Audio("sounds/trumpet.mp3")
				audio.play()
			}
			else{
				parent.classList.add('wrong-opt')
				let audio = new Audio("sounds/fail.mp3")
				audio.play()
			}			

			

		}
	}
	}
</script>

<style lang='sass' scoped>
.articles-test
  @include flexcolumncenter
.options
  width: 100%
  display: flex
  flex-direction: row
  justify-content: space-between
  margin-bottom: 30px
.opt-wrapper
  @include flexcolumncenter
  height: 40px
  padding: 6px
  border-radius: 15%
  background-color: $azure
  box-shadow: 0 5px $shadow
.question-image
  width: 60%
  height: auto
  margin-bottom: 25px
.opt
  font-size: 22px
  text-align: center
.wrong-opt
  background-color: $wrong
  color: #fff
.true-opt
  background-color: $correct
  color: #fff
@media(max-width: 550px)
  .question-image
    width: 80%
  .opt-wrapper
    height: 70px
    width: 30%
  .opt
    font-size: 19px
    font-weight: 300
</style>