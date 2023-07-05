<script>
import {defineComponent} from "vue";
import Navbar from "@/components/navbar.vue";

export default defineComponent({
  components: {Navbar}
})

</script>

<template>
  <header>
  <navbar />
    <img class="header" alt="edinburgh" src="@/assets/img/edinburgh-header.jpg"/>
  </header>

  <main>

  </main>
</template>

<style scoped>
.header {
  max-width: 100%;
}
</style>
