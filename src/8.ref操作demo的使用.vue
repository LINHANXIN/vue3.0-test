<template>
  <div>
    <h1 ref="hRef">哈哈</h1>
  </div>
</template>

<script>
import { onMounted, ref } from "vue";
// ref的使用
export default {
  setup() {
    let hRef = ref(null);
    onMounted(() => {
      console.log(11, hRef.value);
    });
    return {
      hRef,
    };
  },
};
</script>


