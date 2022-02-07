<template>
  <div class = "main">
    <h1 class="main__title">Картины эпохи Возрождения</h1>
    <slot></slot>
  </div>
</template>

<script>


export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Main",
   props:{
    paintings: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style scoped>
.main {
  width: 100%;
  max-width: 1216px;
  min-height: auto;
  margin: 0 auto;
  grid-area: main
}
 .main__title{
   margin: 45px 0;
 }
</style>
