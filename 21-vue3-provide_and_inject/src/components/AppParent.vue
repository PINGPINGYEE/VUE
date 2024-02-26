<template>
  <!-- <AppChild :msg="msg" /> --> <!-- props 사용 -->
  <AppChild :msg="msg" /> <!-- provide, inject 사용 -->
</template>

<script>
import AppChild from './AppChild.vue'

export default {
  components: {
    AppChild
  },
  /*
  props: { // parent는 child와 app 간의 연결만 시키는데도 props를 또 정의 + 그래서 나온 개념이 provide, inject
    msg: {
      type: String,
      default: ''
    }
  }
  */
}
</script>