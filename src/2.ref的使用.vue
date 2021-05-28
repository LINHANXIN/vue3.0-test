<template>
  <div>
    <div>{{ money }}</div>
    <button @click="money++">点击</button>
  </div>
</template>

<script>
// 1.ref函数接受一个简单类型，返回一个响应式的对象
// 2.这个响应式对象只有一个属性 value
// 3.在模板中使用ref,会自动解套
import { ref } from "vue";
export default {
  name: "App",
  setup() {
    const money = ref(100);
    return { money };
  },
};
</script>
