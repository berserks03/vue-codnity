<template>
  <div class="container">
    <LogoSide />
    <LoginSide />
  </div>  
</template>

<script>
import LogoSide from "./LogoSide.vue";
import LoginSide from "./LoginSide.vue";

export default {
  name: "LoginPage",
  components: {
    LogoSide, LoginSide
  },
}
</script>

<style scoped>
.container{
  background: url("../assets/background.png") no-repeat center center fixed;
  background-size: cover;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

@media screen and (min-width: 1024px) {

  .container {
    flex-direction: row;
  }
}
</style>
