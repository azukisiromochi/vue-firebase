<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import { initializeApp } from "firebase/app"
import HelloWorld from './components/HelloWorld.vue'

const config = {
  apiKey: "AIzaSyCb4eKf6YFgicsy0_g7-hqBZ9e6xSanUXk",
  authDomain: "vue-firebase-sample-a6587.firebaseapp.com",
  databaseURL: "https://vue-firebase-sample-a6587.firebaseio.com",
  projectId: "vue-firebase-sample-a6587",
  storageBucket: "vue-firebase-sample-a6587.appspot.com",
  messagingSenderId: "959054759724",
}
initializeApp(config)

export default {
  name: 'App',
  components: {
    HelloWorld
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
