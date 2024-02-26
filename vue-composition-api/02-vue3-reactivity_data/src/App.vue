<template>
  <div @click="increase">{{ count }}</div>
</template>

<script>
import { ref } from 'vue' // ref를 이용하여 초기값을 만듬

export default {
  setup() {
    let count = ref(0)
    function increase() {count.value++} // ref를 쓰지 않으면 반응성이 없음 + count.value를 사용해서 값에 접근해줘야 함
    return {count,increase}
  }
}
</script>