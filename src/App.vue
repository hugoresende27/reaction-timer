<template>
    <h1>Ninja Reactor Time</h1>
    <button @click="start" :disabled="isPlaying">Play</button>

    <Block v-if="isPlaying" :delay="delay"></Block>
  
</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
    }
  },
  components: {
    Block
  },
  methods: {
    start() {
      console.log('start')
      this.delay = 2000 + Math.random() * 3000
      this.isPlaying = true
      console.log(this.delay)
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
