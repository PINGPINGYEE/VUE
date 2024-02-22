<template>
  <h1>{{ msg }}</h1>
  <input type="text" :value="msg" @input="msg = $event.target.value" />
  <br>
  <input type="text" :value="msg" @change="msg = $event.target.value" /> <!-- 입력을 완료가 되면 값이 갱신 -->
  <br>
  <input type="text" v-model.lazy="msg" />
  <input type="text" v-model.number="msg" /> <!-- 입력 값을 숫자 형태로 변경 -->
  <input type="text" v-model.number="msg" />
  <h1>{{ newMsg }}</h1>
  <input type="text" v-model.trim="newMsg" />
</template>

<script>
export default {
  data() {
    return {
      msg: 123,
      newMsg: 'hello world'
    }
  },
  watch: {
    msg() {
      console.log(typeof this.msg)
    },
    newMsg() {
      console.log(this.newMsg)
    }
  }
}
</script>