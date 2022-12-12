<template>
  <div id="app">
    <LoginPage />
  </div>
</template>

<script>
import LoginPage from "../src/components/LoginPage.vue"

export default {
  components: {
    LoginPage
  },  
}
</script>

<style>
@font-face {
  font-family: "AktivGrotesk-Regular";
  src: local("AktivGrotesk-Regular"),
   url("./assets/AktivGrotesk-Regular.ttf") format("truetype");
}

@font-face {
  font-family: "AktivGrotesk-Bold";
  src: local("AktivGrotesk-Bold"),
   url("./assets/AktivGrotesk-Bold.ttf") format("truetype");
}

#app {
  font-family: "AktivGrotesk-Regular", Helvetica, Arial;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  color: #606161;
  line-height: 1.5;
  text-align: left;
  font-size: 2rem;
}

html {
  font-size: 8px;
}
</style>
