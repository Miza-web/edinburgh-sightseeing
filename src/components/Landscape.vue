<script>
import {defineComponent} from "vue";

export default defineComponent({
  data(){
    return {
      hover: false,
      modal : {
        title: "",
        description: "",
        location: "",
        img: "",
        open: false
      }
    }
  },
  methods: {
    openModal(e){
      this.modal.open = !this.modal.open;
      this.$refs.modal.style.display = !this.modal.open ? "none" : "block";
      if (e.target.className === "close") {
        return;
      }
      this.modal.title = e.currentTarget.getElementsByClassName("modalTitle")[0].innerHTML;
      this.modal.description = e.currentTarget.getElementsByClassName("modalDescription")[0].innerHTML;
      this.modal.location = e.currentTarget.getElementsByClassName("modalLocation")[0].innerHTML;
      this.modal.img = e.currentTarget.getElementsByClassName("modalImg")[0].src;
    }
  },
  name: "landscape"
});
</script>
<template>
    <div class="col landscape">
      <h1>Edinburgh's Landscape is one of a kind</h1>
      <h3>Being a coastal city, Edinburgh has access to the sea, while also featuring hills, beautiful architecture and more!</h3>
    </div>
  <div class="container">
    <div class="row">
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false" @click="openModal">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="../components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails modalImg" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
        <div class="modal_desc">
        <h1 class="modalTitle">Arthur's Seat</h1>
        <h3 class="modalDescription">Description placeholder</h3>
        <div class="modalLocation">location</div>
        </div>
      </div>
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false" @click="openModal">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="../components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails modalImg" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
        <div class="modal_desc">
        <h1 class="modalTitle">Portobello Beach</h1>
        <h3 class="modalDescription">Description placeholder</h3>
        <div class="modalLocation">location</div>
        </div>
      </div>
      <div class="col itemsContainer" @mouseover="hover = true" @mouseleave="hover = false" @click="openModal">
        <div class="icon_div" v-if="hover"><img class="fs_icon" src="../components/icons/fullscreen_icon.png"/></div>
        <img class="landscape-thumbnails modalImg" alt="Arthur's seat in Edinburgh" src="@/assets/img/arthurs-seat.jpg">
        <div class="modal_desc">
        <h1 class="modalTitle">Title Placeholder</h1>
        <h3 class="modalDescription">Description placeholder</h3>
        <div class="modalLocation">location</div>
        </div>
      </div>
    </div>
    <div class="modal" ref="modal">
      <div class="modal-content">
        <span class="close" @click="openModal">&times;</span>
        <img class="modal-img" alt="Arthur's seat in Edinburgh" :src="modal.img">
        <h1>{{ this.modal.title }}</h1>
        <h3>{{ this.modal.description }}</h3>
        <div class="modalLocation">{{ this.modal.location }}</div>
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
.modal_desc {
  display: none;
}
</style>