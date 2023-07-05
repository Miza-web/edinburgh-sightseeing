<script>
import {defineComponent} from "vue";
import Navbar from "@/components/navbar.vue";

export default defineComponent({
  data() {
    return {
      show: true
    }
  },
  components: {Navbar}
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
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease-in;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
