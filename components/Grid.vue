<template>
<div class='main-block'>
 <div class="app">
  <div v-for="(option) in allOptions" class="question_block" :style="`background-color: ${option.blockColor}`">
      <h3 class='question-headline'>{{ option.questionTitle }} </h3>    
      <div class="choice-grid">
        <div class="image-wrapper" v-for='(position) in option.choices' :value='`${position.value}`'
        @click='select(position.value, option.name)'>
          <img :src="`/img/${option.name}${position.value}.jpg`" :alt="`${option.name}`">
          <p class="option">{{ position.title }}</p>
        </div>
      </div>      
  </div>

  <button class='submit' type="button" @click='checkResult()'>ПРОВЕРИТЬ</button>
</div>

 <div class='results'>
    <h2>Вы разбираетесь в падежах на <span class='res-percent'>0</span> %.</h2>
      
    <div class='oops'>
      <img src='img/pepa.png'>
      <p>ОБИДНЕНЬКО!</p>
    </div>

    <div class='yeah'>
      <img src='img/pepahappy.png'>
      <p>ХОРОШИЙ РЕЗУЛЬТАТ!</p>
      </div>

    <div class='bad-verdict'>
      <p>Будет неплохо, если вы ознакомитесь с табличкой падежных окончаний -
    правильно говорить и писать существительные - это  <span class='rare'> круто</span>.
      </p>
    <img class='table-image' src='img/table.jpg' alt='russian cases'>
    </div>
  </div>  


</div>
</template>

<script>
 
  export default {
 
  data(){
    return{      
      allOptions:[
      {questionTitle:'Насыпь зерна ... ', name:'horse', choices:[{value:'1',title:'лошадя'},{value:'2', title:'лошадю'},{value:'3', title:'лошаде'},{value:'4', title:'лошади'}], blockColor:'rgba(181, 2, 8,.4)'},
      {questionTitle:'Увидел в подвале ...', name:'mouse', choices:[{value:'1', title:'мыша'},{value:'2', title:'мышу'},{value:'3', title:'мышь'},{value:'4', title:'мыши'}], blockColor:'rgba(212, 103, 2,.4)'},
      {questionTitle:'Она слушает ...', name:'song', choices:[{value:'1',title:'песней'},{value:'2', title:'песен'},{value:'3', title:'песню'},{value:'4', title:'песня'}], blockColor:'rgba(237, 218, 5,.4)'},
      {questionTitle:'Они проводят отпуск во ...', name:'france', choices:[{value:'1',title:'Францие'},{value:'2', title:'Франци'},{value:'3', title:'Францию'},{value:'4', title:'Франции'}],blockColor:'rgba(70, 173, 5,.4)'},
      {questionTitle:'Наша мама скоро родит ...', name:'baby', choices:[{value:'1',title:'ребенку'},{value:'2', title:'ребенка'},{value:'3', title:'ребенком'},{value:'4', title:'ребенки'}], blockColor:'rgba(98, 201, 222,.4)'},      
      {questionTitle:'Извините, у нас сегодня нет ...', name:'meat', choices:[{value:'1',title:'мяса'},{value:'2', title:'мясы'},{value:'3', title:'мясо'},{value:'4', title:'мясов'}], blockColor:'rgba(7, 27, 179,.4)'},
      {questionTitle:'Хвастаюсь новой ...', name:'car', choices:[{value:'1',title:'машиной'},{value:'2', title:'машины'},{value:'3', title:'машином'},{value:'4', title:'машину'}], blockColor:'rgba(53, 43, 59,.4)'}
      ],
      correctAnswers:{'horse':4,'mouse':3,'song':3,'france':4,'baby':2,'meat':1,'car':1}
      ,
      selectedAnswers:{}
}
      
  },
  methods: {
     select(numb, name){      
      this.selectedAnswers[name] = numb
      let momBlock = event.target.parentNode
      for (let i=0;i<momBlock.children.length;i++){
        momBlock.children[i].classList.remove('selected')
      }
      event.target.classList.add('selected')
   
    },
        
    checkResult(){

      function countPercent(sel, corr){
        let counter = 0
        for(let i=0;i<Object.keys(sel).length;i++){        
          if (Object.values(sel)[i]==Object.values(corr)[i]){
            counter++
          }          
        }
        let correctPercent = parseInt(counter/Object.keys(sel).length * 100)
        document.querySelector('.res-percent').textContent = correctPercent
        correctPercent > 60 ? showCongrats(correctPercent):showSorry(correctPercent)
      

      function showCongrats(perc){
        let happypepa = document.querySelector('.yeah')
        happypepa.style.display = 'flex'
      }
      function showSorry(perc){
        let sadpepa = document.querySelector('.oops')
        sadpepa.style.display = 'flex'
        let table = document.querySelector('.bad-verdict')
        table.style.display = 'flex'
      }

    }
      Object.keys(this.selectedAnswers).length==Object.keys(this.correctAnswers).length ? countPercent(this.selectedAnswers,this.correctAnswers):alert('Вы забыли что-то указать!')      
    }  
  }   
} 
</script>

<style lang="sass" scoped>


@font-face
    font-family: 'Rubik'
    font-weight: 600
    src: url('~assets/fonts/Rubik.ttf')


.app
  width: 100%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

.choice-grid
  width: 100%
  max-width: 850px
  display: grid
  margin: auto auto 30px auto
  grid-gap: 10px
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr))

.image-wrapper
  background-color: ghostwhite
  display: flex
  align-items: center
  flex-direction: column
  height: 440px
  width: 370px
  margin: auto
  border-radius: 8px

.option
  font-size: 1.5rem
  font-weight: 600
  text-transform: uppercase
  color: rgba(53, 43, 59,.8)
  position: relative
  bottom: 6px
  margin: 0

img
  margin: 15px auto
  width: 350px
  height: 350px

h4
  margin-top: -1.3rem
  text-align: center
  font-size: 2rem
  color: black

.question_block
  width: 100%
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center

.results
  margin: 1rem auto 2rem auto
  text-align: center
  max-width: 100vw

.bad-verdict
  font-size: 3rem
  display: none
  flex-direction: column
  img
    max-width: 95%

.table-image
  width: auto
  height: auto

.oops, .yeah
  display: flex
  flex-direction: row
  justify-content: center
  font-size: 3rem
  font-weight: 700
  color: #b01a4f
  display: none
  img
    margin: 0

@media(max-width: 500px)
  .oops, .yeah
    flex-direction: column
    width: 95%
    font-size: 2rem

  .bad-verdict
    font-size: 1.5rem
    line-height: 1.6rem

.submit
  margin:1rem auto 1rem auto
  font-size: 20px
  font-family: 'Rubik'
  color: #570b29
  width: 180px
  height: 50px
  border-radius: 2rem
  border: solid 3px #570b29
  background-color: #bcebf7
  box-shadow: 0 5px rgba(0,0,0,.3)

.image-wrapper:hover
  background-color: rgba(0,0,0,.2)
  p
    color: white


.selected
  background-color: rgba(156, 31, 6,.4)
  color: white

@media(max-width: 500px)
  .question__headline
    font-size: 1.5rem
    max-width: 90%
  
  .choice-grid
    grid-template-columns: repeat(auto-fit, minmax(90%, 1fr))
  
  .image-wrapper
    width: 90%
    height: auto
  
  img
    width: 90%
    height: auto
  .submit
    width: 70%
  
</style>