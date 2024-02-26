<template>
  <button @click="message = 'Good?'">Click!</button>
  <h1>App: {{ message }}</h1>
  <!-- <AppParent :msg="message " /> --> <!-- props 사용 -->
  <AppParent  /> <!-- provide, inject 사용 -->
</template>

<script>
import AppParent from './components/AppParent.vue'
import { computed } from 'vue'

export default {
  components: {
    AppParent
  },
  data() {
    return {
      message: 'Hello world!'
    }
  },
  provide() {
    return {
      // msg: this.message // 이렇게 하면 반응성을 제공할 수 없음
      msg: computed(() => this.message) // computed를 만들어서 내부에 callback 함수를 만들어서 데이터를 반환해야 함)
    }
  }
}
</script>

