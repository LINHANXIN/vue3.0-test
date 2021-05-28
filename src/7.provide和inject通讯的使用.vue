<template>
  <div>
    <div>今天天气多少：{{ age }}</div>
    <button @click="age++">增加</button>
    <hr />
    <Demo></Demo>
  </div>
</template>

<script>
import Demo from "./Demo.vue";
import { ref, provide } from "vue";
export default {
  // provide和inject的通讯的使用
  components: {
    Demo,
  },
  setup() {
    let age = ref(10);
    let changeAge = (n) => {
      age.value = n;
    };
    // 父传子
    provide("age", age);
    // 子改变父
    provide("changeAge", changeAge);
    return { age };
  },
};
</script>


