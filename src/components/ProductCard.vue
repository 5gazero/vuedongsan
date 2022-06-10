<template>
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
export default {
  name: "ProductCard",
  props: {
    roomData: Array,
  },
};
</script>

<style>
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
