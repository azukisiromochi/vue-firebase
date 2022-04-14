<template>
  <div id="app">
    <button v-on:click="googleLogin">ログイン</button>
  </div>
</template>

<script>
import { initializeApp } from "firebase/app"
import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth"

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
  methods: {
    googleLogin() {
      const auth = getAuth()
      const provider = new GoogleAuthProvider()
      signInWithPopup(auth, provider)
        .then((result) => {
          const credential = GoogleAuthProvider.credentialFromResult(result)
          const token = credential.accessToken
          const user = result.user
          console.log(token)
          console.log(user)
        }).catch((error) => {
          console.log(error)
        })
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
