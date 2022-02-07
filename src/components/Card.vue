<template>
  <div :key="painting.id" class = "card__wrapper" v-for="painting in paintings">
    <div class = "card">
      <img class = "card__image" :src = painting.slides[0]
           alt = "«Рождение Венеры» Сандро Боттичелли">
      <div class = "card__info">
        <h2>{{painting.pictureTitle}}</h2>
        <div class = "card__sales-area">
          <h5 class = "card__prev-price">{{painting.prevPrice}}</h5>
          <h3 class = "card__price">{{painting.price}}</h3>
          <my-button class="card__btn">Купить</my-button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Card",
props:{
    paintings:{
      type: Array
    }
}
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
.card__image{
  width:100%;
  max-height: 160px;
  object-fit: cover;
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