<template>
  <div class="black-bg" v-if="isModalOpen">
    <div class="white-bg">
      <h4>
        {{ roomData[isClicked].title }}
        <span class="btn" @click="isModalOpen = false">X</span>
      </h4>
      <p>{{ roomData[isClicked].content }}</p>
    </div>
  </div>
  <div class="menu">
    <a v-for="(menu, idx) in menus" :key="idx">{{ menu }}</a>
  </div>
  <DiscountBanner />
  <div v-for="(product, idx) in roomData" :key="idx">
    <img :src="product.image" class="img" />
    <h4
      class="btn"
      @click="
        isModalOpen = true;
        isClicked = idx;
      "
    >
      {{ product.title }}
    </h4>
    <p>월 {{ product.price }} 원</p>
  </div>
</template>

<script>
import DiscountBanner from "./components/DiscountBanner.vue";
import data from "./assets/roomData.js";

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

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 10vh 10vw;
}
.white-bg {
  width: 100%;
  height: 80vh;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
.img {
  margin-top: 20px;
  width: 40vw;
}
.btn {
  cursor: pointer;
}
.btn:hover {
  color: yellowgreen;
}
</style>
