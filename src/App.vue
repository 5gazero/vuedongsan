<template>
  <div class="black-bg" v-if="isModalOpen">
    // true일때만,
    <div class="white-bg">
      <h4>
        상세페이지 <span class="btn" @click="isModalOpen = false">X</span>
      </h4>
      <p>설명</p>
    </div>
  </div>
  <div class="menu">
    <a v-for="(menu, idx) in menus" :key="idx">{{ menu }}</a>
  </div>
  <div v-for="(product, idx) in products" :key="idx">
    <img src="./assets/room0.jpg" class="img" />
    <h4 class="btn" @click="isModalOpen = true">{{ product }}</h4>
    <p>{{ price[idx] }}만원</p>
    <button @click="count[idx]++">허위매물신고</button>
    <span>신고수: {{ count[idx] }}</span>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      isModalOpen: false,
      count: [0, 0, 0],
      menus: ["Home", "Products", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      price: [60, 55, 65],
      images: [
        "./assets/room0.jpg",
        "./assets/room1.jpg",
        "./assets/room2.jpg",
      ],
    };
  },
  methods: {
    increase() {
      this.count++;
    },
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
}
.btn {
  cursor: pointer;
}
.btn:hover {
  color: yellowgreen;
}
</style>
