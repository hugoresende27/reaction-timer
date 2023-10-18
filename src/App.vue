<template>
    <h1>Ninja Reactor Time</h1>
    <button @click="start">Play</button>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      isPlaying: false,
      delay: null,
    }
  },
  components: {
  },
  methods: {
    start() {
      console.log('start')
      this.delay = 2000 + Math.random() * 5000
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
