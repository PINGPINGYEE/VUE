<template>
  <button @click="add">ADD</button>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reverseMessage() }}</h1>
  <h1>{{ reverseMessage() }}</h1>
  <h1>{{ reverseMessage() }}</h1>
</template>

<script>
export default {
  data() {
    return {
      // Getter, Setter(msg는 값을 얻을 수도 있고 지정할 수도 있음)
      msg: 'Hello Computed!'
    }
  },
  computed: {
    // computed에 만든 계산된 데이터는 캐싱되어있기에 출력할 때 추가적인 연산하지 않음(캐싱된 값으로 출력)
    // Getter(reversedMessage는 읽기 전용)
    // reversedMessage() {
    //   return this.msg.split('').reverse().join('')
    // }
    // Getter, Setter
    reversedMessage: {
      get() {
        return this.msg.split('').reverse().join('')
      },
      set(newValue) {
        this.msg = newValue
        console.log(newValue)
      }
    }
  },
  methods: {
    // 호출 시마다 계산
    reverseMessage() {
      return this.msg.split('').reverse().join('')
    },
    add() {
      this.reversedMessage += '!?'
      // this.msg += '!?'
    }
  }
}
</script>