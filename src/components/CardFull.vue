<template>
  <div :key = "painting.id" class = "card__wrapper">
    <div class = "card">
      <SlideShow
          v-for = "(slide, index) in painting.slides"
          :key = "slide"
          :index = "index"
          :visibleSlide = 'visibleSlide'
      @next="next"
      @prev="prev">
        <img class = "card__image" :src = "slide" alt = "«Рождение Венеры» Сандро Боттичелли">
      </SlideShow>

      <div class = "card__info">
        <h2>{{ painting.pictureTitle }}</h2>
        <h4 class = "card__description">{{ painting.pictureDescription }}</h4>
        <div class = "card__sales-area">
          <h5 class = "card__prev-price">{{ painting.prevPrice }}</h5>
          <h3 class = "card__price">{{ painting.price }}</h3>
          <my-button class = "card__btn">Купить</my-button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: "CardFull",
  data() {
    return {
      visibleSlide: 0
    }
  },
  props: {
    painting: {
      type: Object
    }
  },
  methods:{
    next(){
      console.log("next")
      console.log('visibleSlide', this.visibleSlide)
      console.log("painting.slides",this.painting.slides.length)
      if (this.visibleSlide>= this.painting.slides.length-1){

        this.visibleSlide = 0
      }else{
        console.log("next else")
        this.visibleSlide +=1
      }
    },
    prev(){
      console.log("prev")
      if (this.visibleSlide <= 0){
        this.visibleSlide = this.painting.slides.length-1
      }else{
        this.visibleSlide -=1
      }
    }
  }
}
</script>

<style scoped>
.card__wrapper {
  width: 100%;
  max-width: 560px;
  /*height: 328px;*/
  background: inherit;
  margin: 0 auto;
  border: 1px solid #E1E1E1;
}

.card__image {
  width: 100%;
  /*max-height: 320px;*/
  object-fit: cover;
}

.card__info {
  margin: 24px;
  display: grid;
  row-gap: 10px;
}

.card__description {
  text-align: justify;
}

.card__sales-area {
  display: grid;
  grid-template-areas:
  "prev-price button"
  "price button";

  column-gap: 5px;
  grid-template-columns: 45% auto

}

.card__prev-price {
  grid-area: prev-price;
  color: #A0A0A0;
  text-decoration: line-through;

}

.card__price {
  grid-area: price;
}

.card__btn {
  grid-area: button;
  justify-self: end;
}
</style>