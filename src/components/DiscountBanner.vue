<template>
  <div class="banner" v-if="showBanner">지금 결제하면 {{ discount }}% 할인</div>
</template>

<script>
export default {
  name: "DiscountBanner",
  data() {
    return { showBanner: true, discount: 20 };
  },
  mounted() {
    const count = setInterval(() => {
      this.discount--;
      if (this.discount < 1) {
        clearInterval(count);
      }
    }, 1000);
  },
};
</script>

<style>
.banner {
  background: #ededed;
  padding: 1%;
  margin: 0.5% 5%;
  border-radius: 5px;
  font-weight: 600;
}
</style>
