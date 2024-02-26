<template>
  <h1 @click="changeMessage">{{ msg }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Hello?'
    }
  },
  computed: {
    reversedMessage() {
      return this.msg.split('').reverse().join('')
    }
  },
  watch: {
    // msg의 데이터 변경을 감시
    msg(newValue) { // 매개변수 생략 시 아래에 newValue 대신 this.msg 입력
      console.log('msg:', newValue)
    },
    // 계산된 데이터도 감시 가능
    reversedMessage() {
      console.log('reversedMessage: ', this.reversedMessage)
    }
  },
  methods: {
    changeMessage() {
      this.msg = 'Good!'
    }
  }
}
</script>