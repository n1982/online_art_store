<template>
  <button class = "btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button"
}
</script>

<style scoped>
.btn {
  width: 100%;
  max-width: 122px;
  height: 48px;
  color: white;
  background: #403432;
  border: none;
  outline: none;
}
</style>