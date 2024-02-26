<template>
  <MyBtn @listener="log" @change-msg="logMsg">Banana</MyBtn> <!-- HTML 요소에는 카멜 케이스가 되지 않기에 대시 케이스로 수정 -->
</template>

<script>
import MyBtn from './components/MyBtn'

export default {
  components: {
    MyBtn
  },
  methods: {
    log(event) {
      console.log('click!!')
      console.log(event)
    },
    logMsg(msg) {
      console.log(msg)
    }
  }
}
</script>