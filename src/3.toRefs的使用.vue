<template>
  <div>
    <div>{{ money }}</div>
    <button @click="money++">点击</button>
    <div>{{ car.brand }}---{{ car.price }}</div>
    <button @click="car.brand = '宝马'">点击</button>
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  name: "App",
  setup() {
    const state = reactive({
      money: 100,
      car: {
        brand: "奔驰",
        price: 10000,
      },
    });
    return { ...toRefs(state) };
  },
};
</script>
