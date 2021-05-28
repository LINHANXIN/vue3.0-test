<template>
  <div>
    <div>{{ car.brand }}----{{ car.price }}</div>
    <button @click="car.brand = '宝马'">点击</button>
  </div>
</template>

<script>
import { reactive } from "vue";
// 1.reactive的使用,主要用于响应式用的
export default {
  setup() {
    const car = reactive({
      brand: "奔驰",
      price: 100,
    });
    return { car };
  },
};
</script>
