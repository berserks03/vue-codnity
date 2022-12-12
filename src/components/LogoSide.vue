<template>
  <div class="container__logo">
    <div class="logo">
      <img src="../assets/Group 16.svg" alt="logo">
    </div>
    <h1 v-if="isMobile">Built for Logistics Professionals, Perfected for Your Business</h1>
    <h1 v-else>Your Product Our Priority, Shipping made simple</h1>
    <h2>Not a member yet?</h2>
    <p>Please use your personal and company information to Create Account</p>
    <Button>
      <template #text>Create Account</template>
    </Button>
  </div>
</template>

<script>
import Button from "./Button.vue"

export default {
  name: "LogoSide",
  components: {
    Button
  },
  data() {
    return {
      isMobile: false,
    }
  },
  mounted() {
    this.onResize;
    window.addEventListener("resize", this.onResize, true);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.onResize, true);
  },
  methods: {
    onResize() {
      this.isMobile = window.innerWidth < 1024;
    },
  },
}
</script>

<style scoped>
.container__logo {
  background-color: rgba(10,11,9,0.8);
  color: #ffffff;
  flex: 1;
  padding: 3rem;
  justify-content: space-evenly;
  display: flex;
  align-items: center;
  flex-direction: column;
  text-align: center;
}

.logo img {
  width: 210px;
  height: auto;
}

h1 {
  font-size: 1.5rem;
  font-family: "AktivGrotesk-Bold";
}

h2 {  
  font-size: 2rem;
}

p {  
  font-size: 1.5rem;
}

@media screen and (min-width: 1024px) {
  .container__logo {
    padding: 6rem;
    justify-content: normal;
    padding-top: 210px;
    align-items: flex-start;
    text-align: left;
  }

  .logo img {
    width: 600px;
  }

  h1 {
    font-size: 4rem;
  }

  h2 {  
    font-size: 2.25rem;
  }

  p {  
    font-size: 1.75rem;
  }
}
</style>
