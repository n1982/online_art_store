<template>

  <div class = "slide-show" v-show = "visibleSlide === index">
    <slot></slot>
    <button class = "slide-show__button button_left" @click = "next">
      <img
          src = "../../asserts/icon/angle-double-left.svg">
    </button>
    <button class = "slide-show__button button_right" @click = "prev">
      <img
          src = "../../asserts/icon/angle-double-right.svg">
    </button>
  </div>

</template>

<script>
export default {
  name: "SlideShow",
  props: ['visibleSlide', 'index'],
  methods: {
    next() {
      this.$emit("next")
    },
    prev() {
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

.slide-show__button {
  position: absolute;
  height: 40px;
  width: 50px;
  top: calc(50% - 20px);
  left: 0
}

.button_left {
  border: unset;
  background: no-repeat;
}

.button_right {
  left: calc(100% - 50px);
  border: unset;
  background: no-repeat;
}

</style>