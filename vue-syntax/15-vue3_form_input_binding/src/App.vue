<template>
  <h1>{{ msg }}</h1>
  <input type="text" :value="msg" /> <!-- 다음과 같이 데이터를 연결하는 것을 단방향 데이터 바인딩이라고 함 -->
  <h1>{{ newMsg }}</h1>
  <input type="text" :value="newMsg" @input="handler" /> <!-- 다음과 같이 데이터를 연결하는 것을 양방향 데이터 바인딩이라고 함 -->
  <h1>{{ newMsg2 }}</h1>
  <input type="text" :value="newMsg2" @input="newMsg2=$event.target.value" /> <!-- 다음과 같이 하면 핸들러가 필요없음 -->
  <h1>{{ newMsg3 }}</h1>
  <input type="text" v-model="newMsg3" /> <!-- 더욱 단순화 --> <!-- v-model을 이용하여 한글을 작성하게 되면 한 박자가 느림(한 글자가 완성되어야 적용) -->
  <h1>{{ checked }}</h1>
  <input type="checkbox" v-model="checked" />
</template>

<script>
export default {
  data() {
    return {
      msg: 'hello world!',
      newMsg: 'hello world!',
      newMsg2: 'hello world!',
      newMsg3: 'hello world!',
      checked: false
    }
  },
  methods: {
    handler(event) {
      console.log(event.target.value)
      this.newMsg = event.target.value
    }
  }
}
</script>