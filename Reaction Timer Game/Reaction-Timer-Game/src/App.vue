<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue';
export default {
  components: {
      Block,
      Results,
    },
  data(){
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000 ;
      this.isPlaying = true ;
      this.showResults = false ;
      console.log(this.delay) ;
    },
    endGame(reactionTime){
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    }
   
  }
}
</script>

<template>
<h1> XIX_Shadow_XIX Reaction Timer </h1>
<button @click="start" :disabled="isPlaying"> Play</button>
<Block v-if="isPlaying" :delay="delay" @end="endGame"/>
<Results v-if="showResults" :score="score" />
</template>

<style scoped>
h1 {
  padding: 0px 20px;
  background-color: #4441;
  /* border: 1px solid white; */
  border-radius: 10px; 
  font-weight: bold;
  box-shadow: 0px 0px 10px ;
  margin-bottom: 10px;
}

button {
  color:white;
  background-color: blueviolet;
  border: none;
  border-radius: 4px;
  padding: 8px 16px;
  letter-spacing: 1px;
  cursor: pointer;
  font-size: 16px;
  margin: 10px;
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}

@media (min-width: 1024px) {

}
</style>
