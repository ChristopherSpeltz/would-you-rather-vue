<template>
  <div id="app">

    <h1>Would you rather...</h1>

    <would-you-rather
    v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    v-on:answer-changed='answerChanged'
    ></would-you-rather>

    <p> {{ userSelectionMessage }}</p>

  </div>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      wyrQuestion: "Would you rather be incredibly lucky with average intelligence or incredibly smart with average luck?",
      wyrAnswer1: 'Incredibly lucky with average intelligence',
      wyrAnswer2: 'Incredibly smart with average luck',
      userSelectionMessage: ''
    }
  },
  methods: {
    answerChanged(choice) {
      this.userSelectionMessage = `Thanks! You chose ${choice}`
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
