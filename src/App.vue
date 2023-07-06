<script>
import {defineComponent} from "vue";
import navbar from "@/components/navbar.vue";
import footer_main from "@/components/footer_main.vue";

export default defineComponent({
  data() {
    return {
      show: true,
      hover: false
    }
  },
  components: {navbar, footer_main}
},)

</script>

<template>
  <header>
  <navbar />
    <div>
    <img class="header" alt="edinburgh" src="@/assets/img/edinburgh-header.jpg"/>
      <transition appear>
      <div class="header-text" v-if="show">Discover Edinburgh</div>
      </transition>
    </div>
  </header>

  <main>
    <div class="col landscape">
      <h1>Edinburgh's Landscape is one of a kind</h1>
      <h3>Being a coastal city, Edinburgh has access to the sea, while also featuring hills, beautiful architecture and more!</h3>
    </div>
  <div class="container">
    <div class="row">
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="./components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
      </div>
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="./components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
      </div>
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="./components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
      </div>
    </div>
    </div>
    <footer_main />
  </main>
</template>

<style scoped>
.header {
  max-width: 100%;
}
.header-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 110px;
  color: white;
  text-shadow: 3px 3px black;
}
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
