<template>
  <div>
    儿子的天气：{{ age }}
    <button @click="handleClick">修改</button>
    <hello></hello>
  </div>
</template>

<script>
import { inject } from "vue";
import hello from './hello.vue'
export default {
  components:{
    hello
  },
  setup() {
    const age = inject("age");
    const changeAge = inject('changeAge')
    const handleClick = () => {
      changeAge(2000)
    };
    return { age, handleClick };
  },
};
</script>

