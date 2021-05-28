<template>
  <div>
    <div>{{ money }}</div>
    <button @click="money++">点击</button>
    <div>{{ car.brand }}---{{ car.price }}</div>
    <button @click="car.brand = '宝马'">点击</button>
  </div>
</template>

<script>
import { reactive, ref, toRefs, readonly } from "vue";
export default {
  name: "App",
  setup() {
    const money = ref(100);
    const car = readonly({
      brand: "奔驰",
      price: 100000,
    });
    return {
      money: readonly(money),
      car: car,
    };
  },
};
</script>
