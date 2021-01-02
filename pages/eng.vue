<template>
  <div class="page-wrapper">
     <div class="theory">
       <h2 class="section-headline">артикли</h2>
       <p>Обычно перед существительными нужен артикль - небольшая часть речи, которая будет указывать, определенное это существительное, или нет (артикли и сами бывают определенные - <span class='highlighted'>"the"</span> и неопределенные - <span class='highlighted'>"a"</span> / <span class='highlighted'>"an"</span>). Это помогает понять, обсуждаем мы знакомый предмет, или раньше никогда его не видели/не обсуждали.</p> 
              
       <div class='examples'>

       	<div class='indefinite'>
        <p>Если мы впервые начинаем говорить про какой-то предмет или существо, понадобится неопределенный артикль:
        	<div class='example-indefinite'>
        	<p>I see <span class='highlighted'>a</span> cat! ("Я вижу кошку" - скажем мы, выглянув из окна. <span class='smaller'>Это незнакомая кошка.</span> )</p>
        	<img src='/img/unnamed.jpg'/>
        	</div>
        </div>
      
        <div class="definite">
 			<p style='margin-top: 30px'>Теперь, когда мы уже разок упоминали эту кошку, будем использовать определенный артикль the, если продолжим про нее говорить:</p>
        	<div class='example-definite'>
        	<p><span class='highlighted'>The</span> cat is licking its leg! ("Кошка <span class='smaller'>
        	<<i>про которую мы только что уже говорили</i>></span> лижет свою лапку!")</p>
        	<img src="/img/tenor.gif"/>
        </div>
      	</div>
      </div>

       <p>Бывают ситуации, когда <span class='highlighted'>артикль не нужен</span>, потому что перед существительным уже есть какое-то слово, заменяющее артикль: притяжательное местоимение (my, his, her итд.), this или that, любое числительное (one, two, three). Например: <br>I have a sister. (У меня есть сестра) - <i>нужен</i><br>
        <span class='highlighted'>My</span> sister is beautiful. (<span class='highlighted'>Моя</span> сестра красивая) - <i>не нужен</i><br>
        I have <span class='highlighted'>one</span> sister. (У меня есть <span class='highlighted'>одна</span> сестра) - <i>не нужен</i><br>

        <br>Еще нам не понадобится артикль a/an перед существительными во множественном числе: <br> I have a book. У меня есть книга. /
       I have books. У меня есть книги.</p>


    </div>
  </div>
</template>

<script>

export default {
  
}
</script>

<style scoped lang='sass'>
.theory
	width: 90%
	display: flex
	flex-direction: column
	justify-content: center
	p
		font-size: 20px
		margin: auto

.examples
	margin-top: 30px
	width: 100%
	display: flex
	flex-direction: row
	justify-content: space-between

.definite, .indefinite
	display: flex
	flex-direction: column
	width: 48%
	border: 2px dotted black
	padding: 5px
	height: 100%
.example-definite
	p
		margin-right: 10px
.example-indefinite, .example-definite
	display: flex
	flex-direction: row
img
	width: 200px
	height: auto
.smaller
	font-size: 16px
.highlighted
	color: rgba(135, 12, 55, .8)
@media(max-width: 500px)
	.examples, .example-indefinite, .example-definite
		flex-direction: column
		justify-content: center
	.definite, .indefinite
		width: 100%


</style>
