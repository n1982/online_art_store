<template>
  <div class = "card__wrapper">
    <div :class = "{sold:painting.price>=0}">
      <div class = "card">
        <img class = "card__image" :src = painting.slides[0]
             alt = {{painting.pictureTitle}}>
        <div class = "card__info">
          <h2 class = "card__title" @click = "showFullCard(painting.id)">{{ painting.pictureTitle }}</h2>
          <div class = "card__sales-area">
            <h5 class = "card__prev-price">{{ painting.prevPrice }}</h5>
            <h3 class = "card__price">{{ painting.price }}</h3>
            <my-button v-if = "painting.price" @btnClick = "btnClick(painting.id)"
                       :class = "{card__btn: true, disabled: btnDisabled, inBasket: inBasket }">{{ btnText }}
            </my-button>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Card",
  props: {
    painting: {
      type: Object
    }
  },
  data() {
    return {
      btnText: `Купить`,
      btnDisabled: false,
      name: this.painting.id,
      inBasket: false
    }
  },
  mounted() {
    console.log("name", this.name)

    if (localStorage[this.name]) {
      this.btnText = localStorage[this.name];
      this.inBasket = true;
    }
  },

  methods: {
    showFullCard(data) {
      this.$emit("showFullCard", data - 1)
    },

    btnClick() {

      this.btnText = 'Обрабатывается'
      this.btnDisabled = true
      setTimeout(() => {
        this.btnText = 'В корзине'
        this.btnDisabled = false
        this.inBasket = true
        localStorage[this.name] = 'В корзине';


      }, 2000)
    },
  }
}
</script>

<style scoped>
.card__wrapper {
  display: block;
  position: relative;
  width: 100%;
  max-width: 280px;
  height: 328px;
  background: inherit;
  margin: 0 auto;
  border: 1px solid #E1E1E1;
}

.card__image {
  width: 100%;
  max-height: 160px;
  object-fit: cover;
  z-index: 0;
}

.card__info {
  margin: 24px;
}

.card__title {
  cursor: pointer;
}

.card__sales-area {
  display: grid;
  grid-template-areas:
  "prev-price button"
  "price button";
  margin-top: 22px;
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
}

.disabled,
.disabled:hover {
  background: #C1B4B1;
  cursor: unset;
}

.sold {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: white;
  top: 0;
  right: 0;
  opacity: 0.5;
  z-index: 3;
}

.inBasket {
  background: #5B3A32;
}
</style>