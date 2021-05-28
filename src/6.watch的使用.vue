<template>
  <div>
    <div>今年多少岁：{{ age }}</div>
    <button @click="age++">修改年龄</button>
    <div>车的类型：{{ car.brand }}</div>
    <button @click="car.brand = '宝马'">改变</button>
  </div>
</template>

<script>
// watch监听属性的使用
import { toRefs, reactive, watch, ref } from "vue";
export default {
  setup() {
    let active = reactive({
      age: 10,
      car: {
        brand: "奔驰",
      },
    });
    // watch接受3个参数
    // 参数1：监视的数据源，可以是一个ref或者一个函数
    // 参数2：回调函数(value,oldValue)=>{}
    // 参数3：额外的配置 是一个对象{deep:true,immediate:true}
    // watch(
    //   () => active.age,
    //   (value, olaValue) => {
    //     console.log(11, value, olaValue);
    //   }
    // );

    // ref的watch监听
    // const age = ref(10);
    // watch(age, (value, oldValue) => {
    //   console.log(11, value, oldValue);
    // });

    // 监听对象
    // watch(
    //   () => active.car,
    //   (value, oldValue) => {
    //     console.log(11, value, oldValue);
    //   },
    //   { deep: true, immediate: true }
    // );

    // 监听多个值
    // watch(
    //   [() => active.age, () => active.car],
    //   ([age, car]) => {
    //     console.log(11, age, car);
    //   },
    //   { deep: true }
    // );

    // 监听整个reactive
    watch(active, (value, oldValue) => {
      console.log(11, value, oldValue);
    });

    return { ...toRefs(active) };
  },
};
</script>

