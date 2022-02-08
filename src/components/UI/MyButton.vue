<template>
  <button @click="handleClick" class = "btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button",
emits: ['btnClick'],
  methods:{
    handleClick(){
      this.$emit('btnClick')
    }
  }
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
  cursor: pointer;
}
.btn:hover{
  background: #776763;

}
</style>