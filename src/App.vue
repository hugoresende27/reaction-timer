<template>
    <h1>Ninja Reactor Time</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <a href="/">
      <button>Reload</button>
    </a>
    <Block v-if="isPlaying" :delay="delay" @end="endGame"></Block>
    <Results v-if="showResults" :score="score"></Results>

   
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults : false
    }
  },
  components: {
    Block,
    Results
  },
  methods: {
    start() {
      // this.delay = 2000 + Math.random() * 5000
      this.delay =  Math.random() * 2000
      this.isPlaying = true
      this.showResults = false
      console.log(this.delay)
    },
    endGame(reactTime) {
      this.score = reactTime
      this.isPlaying = false
      this.showResults = true
    }
  }
}
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
