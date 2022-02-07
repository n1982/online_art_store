<template>
  <div class = "slide-show" v-show = "visibleSlide === index">
    <slot></slot>
    <button class = "slide-show__button button_left" @click = "next">Next</button>
    <button class = "slide-show__button button_right" @click = "prev">Prev</button>
  </div>
</template>

<script>
export default {
  name: "SlideShow",
  props: ['visibleSlide', 'index'],
  methods:{
    next(){
      this.$emit("next")
    },
    prev(){
      this.$emit("prev")

    },
  }
}
</script>

<style scoped>
.slide-show {
  position: relative;
  max-width: 560px;
  max-height: 320px;
  overflow: hidden;
}

button {
  position: absolute;
  height: 40px;
  width: 50px;
  top: calc(50% - 20px);
  left: 0
}

.button_left {

}

.button_right {

  left: calc(100% - 50px);

}
</style>