<template>
<div class="pop-up" v-if="showPopUp" @click="hidePopUpWindow" >
  <div class="pop-up__content" @click.stop>
  <slot></slot>
  </div>
</div>
</template>

<script>
export default {
  name: "PopUpWindow",
 props:{
   showPopUp:{
    type: Boolean,
     default: false
  }
 },
 methods:{
   hidePopUpWindow(){
     this.$emit('update:showPopUp', false)
   }
 }
}
</script>

<style scoped>
.pop-up{
  top:0;
  bottom: 0;
  right:0;
  left: 0;
  background: rgba(255,255,255, 0.7);
  position: fixed;
  display: flex;
}
.pop-up__content{
  margin: auto;
  background-color: inherit;
}
</style>