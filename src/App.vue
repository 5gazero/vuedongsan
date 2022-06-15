<template>
  <transition name="fade">
    <DetailModal
      @closeModal="isModalOpen = false"
      :roomData="roomData"
      :isClicked="isClicked"
      :isModalOpen="isModalOpen"
    />
  </transition>
  <div class="menu">
    <a v-for="(menu, idx) in menus" :key="idx">{{ menu }}</a>
  </div>
  <DiscountBanner />
  <Card
    @openModal="
      isModalOpen = true;
      isClicked = $event;
    "
    :roomData="roomData"
  />
</template>

<script>
import DiscountBanner from "./components/DiscountBanner.vue";
import data from "./assets/roomData.js";
import DetailModal from "./components/DetailModal.vue";
import Card from "./components/ProductCard.vue";

export default {
  name: "App",
  data() {
    return {
      roomData: data,
      isModalOpen: false,
      isClicked: 0,
      count: [0, 0, 0],
      menus: ["Home", "Products", "About"],
    };
  },
  components: {
    DiscountBanner,
    DetailModal,
    Card,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

.menu {
  background: yellowgreen;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
  font-weight: 600;
}

.fade-enter-from {
  transform: translateY(-1000px);
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  transform: translateY(0px);
}
.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: all 1s;
}
.fade-leave-to {
  opacity: 0;
}
</style>
