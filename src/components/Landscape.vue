<script>
import {defineComponent} from "vue";

export default defineComponent({
  data(){
    return {
      hover: false
    }
  },
  name: "landscape",
});
</script>
<template>
    <div class="col landscape">
      <h1>Edinburgh's Landscape is one of a kind</h1>
      <h3>Being a coastal city, Edinburgh has access to the sea, while also featuring hills, beautiful architecture and more!</h3>
    </div>
  <div class="container">
    <div class="row">
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="../components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
      </div>
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="../components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
      </div>
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="../components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
      </div>
    </div>
    </div>
</template>
<style scoped>
.landscape {
  margin-top: 20px;
  text-align: center;
}
.landscape-thumbnails {
  width: 330px;
}
.landscape-thumbnails:hover {
  opacity: 0.5;
  border: 1px solid black;
}
.itemsContainer {
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
}
.itemsContainer:hover .icon_div{display:block}
.icon_div {
  position: absolute;
  display: none;
  width: 50px;
}
.fs_icon {
  width: 75px;
}
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease-in;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>