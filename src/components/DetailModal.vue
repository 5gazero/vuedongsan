<template>
  <div class="black-bg" v-if="isModalOpen">
    <div class="white-bg">
      <h4>
        {{ roomData[isClicked].title }}
        <span class="btn" @click="$emit('closeModal')">ⓧ</span>
      </h4>
      <p>{{ roomData[isClicked].content }}</p>
      <div><img :src="roomData[isClicked].image" class="img" /></div>
      <input v-model="month" />
      <p>{{ month }}개월 {{ roomData[isClicked].price * month }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailModal",
  props: {
    isModalOpen: Boolean,
    roomData: Array,
    isClicked: Number,
  },
  data() {
    return {
      month: 1,
    };
  },
};
</script>

<style>
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
</style>
