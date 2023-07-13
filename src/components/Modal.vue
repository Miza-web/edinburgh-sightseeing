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
    openModal(){
      this.modal.open = !this.modal.open;
    }
  },
  name: "Modal",
  props: ["title", "description", "location", "img"],
},
);
</script>

<template>
        <div v-if="modal.open">
      <div class="modal-content">
        <span class="close" @click="openModal">&times;</span>
        <img class="modal-img" alt="Arthur's seat in Edinburgh" :src="img">
        <h1>{{ title }}</h1>
        <h3>{{ description }}</h3>
        <div class="modalLocation">{{ location }}</div>
      </div>
      </div>
</template>

<style scoped>

</style>