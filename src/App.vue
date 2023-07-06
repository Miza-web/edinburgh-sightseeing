<script>
import {defineComponent} from "vue";
import navbar from "@/components/navbar.vue";
import footer_main from "@/components/footer_main.vue";
import header_main from "@/components/Header_main.vue";
import landscape from "@/components/landscape.vue";
import history from "@/components/History.vue";
import tourism from "@/components/Tourism.vue";

export default defineComponent({
  components: {navbar, footer_main, header_main, landscape, history, tourism}
},)

</script>

<template>
  <header>
  <navbar />
  <header_main />
  </header>
  <main>
    <landscape />
    <footer_main />
  </main>
</template>

<style scoped>

</style>
