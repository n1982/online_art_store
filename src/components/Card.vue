<template>
  <div class = "card__wrapper">
    <div class = "card">
      <img class = "card__image" src = "../asserts/img/card1/painting-6318612801.png"
           alt = "«Рождение Венеры» Сандро Боттичелли">
      <div class = "card__info">
        <h2>«Рождение Венеры» Сандро Боттичелли</h2>
        <div class = "card__sales-area">
          <h5 class = "card__prev-price">2 000 000 $</h5>
          <h3 class = "card__price">5 000 000 $</h3>
          <my-button class="card__btn">Купить</my-button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "Card",

}
</script>

<style scoped>
.card__wrapper {
  width: 100%;
  max-width: 280px;
  height: 328px;
  background: inherit;
  margin: 0 auto;
  border: 1px solid #E1E1E1;
}
.card__info{
  margin: 24px;
}
.card__sales-area{
  display: grid;
  grid-template-areas:
  "prev-price button"
  "price button";
  margin-top: 22px;
  column-gap: 5px;
  grid-template-columns: 45% auto

}
.card__prev-price{
  grid-area: prev-price;
  color:#A0A0A0;
  text-decoration: line-through;

}

.card__price{
  grid-area: price;
}
.card__btn{
  grid-area: button;
}
</style>