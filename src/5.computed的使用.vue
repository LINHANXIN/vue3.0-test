<template>
  <div>
    <input type="text" v-model="age" />
    <input type="text" v-model="nextAge" />
    <input type="text" v-model="nextAge2">
  </div>
</template>

<script>
// computed计算属性的使用
import { ref, computed } from "vue";
export default {
  setup() {
    let age = ref(10);
    // 1.computed是一个函数
    // 传入一个函数getter返回一个不允许修改的计算属性
    let nextAge = computed(() => {
      return parseInt(age.value) + 1;
    });
    // 2.传入一个对象，包括get和set,可以创建一个可以修改的计算属性
    let nextAge2 = computed({
      get() {
        return parseInt(age.value) + 2;
      },
      set(value) {
        return (age.value = value - 2);
      },
    });
    return { age, nextAge,nextAge2 };
  },
};
</script>

