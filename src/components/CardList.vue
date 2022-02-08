<template>
  <div class="card-list" >
<slot></slot>
  </div>
</template>

<script>


export default {
  name: "CardList",

}
</script>

<style scoped>
.card-list{
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  grid-gap: 10px;
}
</style>