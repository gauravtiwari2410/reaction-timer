<template>
  <h1>Reaction Timer</h1>
  <button  @click="start" :disabled="isPlaying">Play</button>
  <ContentBlock v-if="isPlaying" :delaytime="delay" @end="endGame"/>
  <!-- <p v-if="showResult">Reaction time: {{ score }} ms</p> -->
  <ResultsBlock v-if="showResult" :score="score"/>
</template>

<script>
// Import the component
import ContentBlock from "./components/ContentBlock.vue";
import ResultsBlock from './components/ResultsBlock.vue';

export default {
  name: 'App',
  // Register the component
  components: { ContentBlock, ResultsBlock },
  data() {
    return {
      isPlaying: false,
      delay: 0,
      score: 0,
      showResult:false
    };
  },
  methods: {
    start() {
      this.delay = 0;
      this.isPlaying = true;
      console.log(this.delay);
      this.showResult=false
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult=true;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}
</style>
