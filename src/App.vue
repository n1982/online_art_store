<template>
  <div class = "app-wrapper">
    <div class = "app">

      <Header />

      <Main >
        <CardList >
          <Card  :paintings="paintings" @showFullCard="showFullCard"/>
        </CardList>
      </Main>
      <Footer />
      <PopUpWindow v-model:showPopUp="showPopUp">
        <CardFull :painting= 'paintings[cardId]' />
      </PopUpWindow>
    </div>
  </div>
</template>

<script>


export default {
  name: 'app',
  data() {
    return {
      paintings: [
        {
          id: 1,
          pictureTitle: '«Рождение Венеры» Сандро Боттичелли',
          pictureDescription: 'Картина итальянского художника тосканской школы Сандро Боттичелли. Представляет собой живопись темперой на холсте размером 172,5 × 278,5 см. В настоящее время хранится в галерее Уффици, Флоренция.',
          slides:[
            "../asserts/img/card_1/slide_1.jpg",
            "../asserts/img/card_1/slide_2.jpg",
            "../asserts/img/card_1/slide_3.jpg",
            "../asserts/img/card_1/slide_4.jpg",
          ],
          prevPrice:"2 000 000$",
          price:"1 000 000$"
        },
        {
          id: 2,
          pictureTitle: '«Тайная вечеря»  Леонардо да Винчи',
          pictureDescription: 'Тайная вечеря Леонардо более известная под названием «Ченаколо», или «Последняя трапеза». Леонардо да Винчи трудился над ней с 1494 по 1498 год.',
          slides:[
            "../asserts/img/card_2/slide_1.jpg",
            "../asserts/img/card_2/slide_2.jpg",
            "../asserts/img/card_2/slide_3.jpg",
            "../asserts/img/card_2/slide_4.jpg",

          ],
          prevPrice: null,
          price:"3 000 000$"
        },
        {
          id: 3,
          pictureTitle: '«Сотворение Адама» Микеланджело',
          pictureDescription: 'Эта фреска была написана Микеланджело в 1511 году. Великий тосканский мастер получил заказ от Папы Юлия II несколькими годами ранее, в 1508 году, для  создания фрески свода Сикстинской капеллы в Риме.',
          slides:[
            "../asserts/img/card_3/slide_1.jpg",
            "../asserts/img/card_3/slide_2.jpg",
            "../asserts/img/card_3/slide_3.jpg",
            "../asserts/img/card_3/slide_4.jpg",

          ],
          prevPrice: "6 000 000$",
          price:"5 000 000$"
        },
        {
          id: 4,
          pictureTitle: '«Урок анатомии»  Рембрандт',
          pictureDescription: '«Урок анатомии доктора Тульпа» – один из самых узнаваемых образов в истории живописи, созданный 25-летним Рембрандтом после переезда из родного Лейдена в Амстердам.',
          slides:[
            "../asserts/img/card_4/slide_1.jpg",
            "../asserts/img/card_4/slide_2.jpg",
            "../asserts/img/card_4/slide_3.jpg",
            "../asserts/img/card_4/slide_4.jpg",

          ],
          prevPrice: null,
          price: null
        },
      ],
      showPopUp:false,
      cardId:0
    }
  },
  methods:{
    showFullCard(id){
      console.log("Событие перехвачено")
      console.log("data", id)
      this.showPopUp = true
      this.cardId = id
    }
  }
}

</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Merriweather', serif;
  font-style: normal;
}
body{
  height: 100%;
}
.app-wrapper {
  width: 100%;
  background-color: #F6F3F3;
}

.app {
  max-width: 1920px;
  padding: 10px;
  min-height: 100vh;
  margin: auto;
  display: grid;
  grid-template-areas:
    "header"
    "main"
    "footer";
  grid-template-rows: 97px 1fr 97px;
  grid-template-columns: 1fr;
  grid-gap: 20px;
}


h1 {
  font-weight: bold;
  font-size: 24px;
  line-height: 39px;
}

h2 {
  font-weight: normal;
  font-size: 18px;
  line-height: 27px;
}

h3 {
  font-weight: bold;
  font-size: 16px;
  line-height: 24px;
}

h4 {
  font-weight: bold;
  font-size: 14px;
  line-height: 21px;
}

h5 {
  font-weight: normal;
  font-size: 14px;
  line-height: 21px;
}

h6 {
  font-weight: lighter;
  font-size: 14px;
  line-height: 21px;
}

</style>