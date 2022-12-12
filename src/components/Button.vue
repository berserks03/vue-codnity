<template>
  <button class="btn" :class="{'btn--login': isLogin}">
    <slot name="text" />
  </button>
</template>

<script>
export default {
  name: "ButtonComponent",
  props: {
    isLogin: {
      type: Boolean,
      default: false,
    }
  }
}
</script>

<style scoped>
.btn {
  min-width: 120px;
  height: 4rem;
  font-size: 1.75rem;
  border: 1px solid #ffffff;
  border-radius: 0.5rem;
  background-color: transparent;
  color: #ffffff;
  cursor: pointer;
}

.btn--login {
  float: right;
  background-color: #fed800;
  border: none;
  color: #1c1c1c;
}
</style>
