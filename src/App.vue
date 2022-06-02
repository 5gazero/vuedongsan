<template>
  <div class="menu">
    <a v-for="(menu, idx) in menus" :key="idx">{{ menu }}</a>
  </div>
  <div>
    <h4 v-for="(product, idx) in products" :key="idx">{{ product }}</h4>
    <p>{{ price }}만원</p>
    <button @click="increase">허위매물신고</button>
    <span>신고수: {{ count }}</span>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      count: 0,
      menus: ["Home", "Products", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      price: 60,
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
</style>
