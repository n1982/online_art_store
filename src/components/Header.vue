<template>
  <div class = "header">
    <a href = "#"><h5>Каталог</h5></a>
    <a href = "#"><h5>Доставка</h5></a>
    <a href = "#"><h5>Оплата</h5></a>
    <a href = "#"><h5>Контакты</h5></a>
    <a href = "#"><h5>О компании</h5></a>
    <div class = "header__search">
      <input v-model.trim = "searchQuery" type = "text" placeholder = "поиск по названию картины">
      <my-button @click = "searchPainting" class = "btn">Найти!</my-button>
    </div>
  </div>
</template>

<script>

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Header",
  data() {
    return {
      searchQuery: ''
    }
  },
  methods: {
    searchPainting() {
      this.$emit('searchPainting', this.searchQuery)
    }
  }
}
</script>

<style scoped>
a,
a:active,
a:hover {
  text-decoration: none;
  color: black;
}

@media (max-width: 630px) {
  h5 {
    font-size: 10px;
  }

}

.header {
  max-width: 1216px;
  width: 100%;
  height: 97px;
  margin: auto;
  grid-area: header;
  align-self: flex-start;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  border-bottom: 1px solid #E1E1E1;
}

.header__search {
  max-width: 416px;
  display: flex;
  flex-grow: 1;
  justify-content: flex-end;
}

input {
  width: 100%;
  max-width: 416px;
  height: 48px;
  border: 1px solid #E1E1E1;
  padding: 10px;
  background-color: inherit;
  outline: none;
}

</style>