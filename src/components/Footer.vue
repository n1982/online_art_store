<template>
  <div class = "footer">
    <a href = "#"><h5>Каталог</h5></a>
    <a href = "#"><h5>Доставка</h5></a>
    <a href = "#"><h5>Оплата</h5></a>
    <a href = "#"><h5>Контакты</h5></a>
    <a href = "#"><h5>О компании</h5></a>
    <div class = "footer__contacts">
      <img src = "../asserts/icon/phone.svg" alt = "icon">
      <h5>+7 (812) 555-55-55</h5>
      <img src = "../asserts/icon/coordinate_point.svg" alt = "icon">
      <h5>г. Санкт-Петербург, ул. Ефимова, 3</h5>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Footer"
}
</script>

<style scoped>
.footer {
  grid-area: footer;
  max-width: 1216px;
  width: 100%;
  min-height: 97px;
  margin: auto;
  align-self: flex-start;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  border-bottom: 1px solid #E1E1E1;
}

a,
a:active,
a:hover {
  text-decoration: none;
  color: black;
}

.footer__contacts {
  max-width: 481px;
  display: flex;
  flex-grow: 1;
  justify-content: space-between;
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