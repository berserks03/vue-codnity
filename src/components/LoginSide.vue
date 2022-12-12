<template>
  <div class="container__login">
      <div class="login__form">
        <h1>Welcome back!</h1>
        <p>Please login to your account</p>
        <form>
          <div class="input-block">
            <input
              type="text"
              name="email"
              class="input-text"
              required
            >
            <span class="placeholder">
              EMAIL
            </span>
          </div>
          <div class="input-block">
            <input
              type="password"
              name="password"
              class="input-text"
              id="password"
              required
            >
            <span class="placeholder">
              PASSWORD
            </span>
            <img  v-if="isVisible" @click="toggleVisibility()" class="visibility" src="../assets/eye-open.svg" alt="icon">
            <img v-else @click="toggleVisibility()" class="visibility" src="../assets/eye-closed.svg" alt="icon">
          </div>
          <div class="checkbox-container">
            <label class="keep-logged" for="keep-logged">
              <input type="checkbox" id="keep-logged">
              Keep me logged in
              <span class="checkmark"></span>
            </label>
            <div class="forgot"><a href="/">Forgot password?</a></div>
          </div>
          <div class="button-container--right">
            <Button isLogin>
              <template #text>Log in</template>
            </Button>
          </div>
        </form>
      </div>
    </div>
</template>

<script>
import Button from "./Button.vue"

export default {
  name: "LoginSide",
  components: {
    Button
  },
  data() {
    return {
      isVisible: false,
    }
  },
  methods: {
    toggleVisibility() {
      const input = document.getElementById("password");
      if (input.type === "password") {
        input.type = "text";
        this.isVisible = true;
      } else {
        input.type = "password";
        this.isVisible = false;
      }
    },
  },
}
</script>

<style scoped>
.container__login {
  background-color: #ffffff;
  display: flex;
  flex: 1;
  align-items: center;
  flex-direction: column;
  padding: 6rem 3rem 3rem;
  justify-content: space-evenly;
}

.login__form {
  width: 100%;
}

div.input-block {
  position: relative;
  margin-bottom: 2rem;
}

div.input-block input {
  font-size: 1.75rem;
  color: #606161;
  width: calc(100% - 34px);
  padding: 15px 15px;
  border-radius: 1rem;
  border: 2px solid  #d1d3d4;
  outline:none;
}

div.input-block span.placeholder {
  position: absolute;
  margin: 17px 0;
  font-family: "AktivGrotesk-Bold";
  color:  #343a40;
  display: flex;
  align-items: center;
  font-size: 1.25rem;
  top: 0;
  left: 17px;
  transition: all 0.2s;
  transform-origin: 0% 0%;
  background: none;
  pointer-events: none;
}

div.input-block input:valid + span.placeholder,
div.input-block input:focus + span.placeholder {
  transform: translateY(-23px);
  background: #ffffff;
}

.input-text {
  width: calc(100% - 34px);
}

.visibility {
  position: absolute;
  right: 16px;
  top: 14px;
  cursor: pointer;
}

.checkbox-container {
  display: flex;
  justify-content: space-between;
  font-size: 1.75rem;
  margin-bottom: 3rem;
}

.keep-logged {
  position: relative;
  padding-left: 3rem;
}

.keep-logged input {
  opacity: 0;
  height: 0;
  width: 0;
}

.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 16px;
  width: 16px;
  border: 1px solid #d1d3d4;
  cursor: pointer;
}

.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

.keep-logged input:checked ~ .checkmark {
  border-color: #fed800;
}
.keep-logged input:checked ~ .checkmark:after {
  display: block;
}
.keep-logged .checkmark:after {
  left: 5px;
  top: 0;
  width: 5px;
  height: 10px;
  border: solid #fed800;
  border-width: 0 3px 3px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}

.forgot a {
  display: inline-block;
  border-bottom: 2px solid #fed800;
  color: #1c1c1c;
  text-decoration: none;
}

.button-container--right {
  text-align: right;
}

@media screen and (min-width: 1024px) {

  .container__login {
    padding-top: 220px;
    justify-content: normal;
  }
}
</style>
