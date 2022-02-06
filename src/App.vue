<template>
  <div class="app-wrapper">
  <div class = "app">
    <Header />
    <Main/>
    <Footer/>
  </div>
  </div>
</template>

<script>


import Main from "./components/Main";
import Footer from "./components/Footer";
export default {
  name: 'app',
  components: {Footer, Main},
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
.app-wrapper{
  width: 100%;
  height: 100vh;
  background-color: #F6F3F3;
}

.app {
  max-width: 1920px;
  padding: 10px;
  height: 100vh;
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