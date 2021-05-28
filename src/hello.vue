<template>
  <div>
    孙子组件:{{ age }}
    <button @click="handleClick">修改</button>
  </div>
</template>

<script>
import { inject } from "vue";
export default {
  setup() {
    const age = inject("age");
    const changeAge = inject('changeAge')
    const handleClick = () => {
      changeAge(1000);
    };
    return { age, handleClick };
  },
};
</script>

