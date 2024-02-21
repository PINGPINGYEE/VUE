<template>
  <div>
    <h1>enter</h1>
    <input type="text" @keydown="handlerA" />
    <input type="text" @keydown.enter="handlerB" /> <!-- template에서 enter는 케밥 케이스로 작성 -->
    <h1>a</h1>
    <input type="text" @keydown.a="handlerC" /> <!-- template에서 enter는 케밥 케이스로 작성 -->
    <h1>ctrl + shift + a</h1>
    <input type="text" @keydown.ctrl.shift.a="handlerD" /> <!-- template에서 enter는 케밥 케이스로 작성 -->
  </div>
</template>

<script>
export default {
  methods: {
    handlerA(event) {
      if (event.key === 'Enter') { // script에서 Enter는 파스칼 케이스로 작성
        console.log('Enter!!')
      }
      // console.log(event)
    },
    handlerB() {
      console.log('Enter!!')
    },
    handlerC() {
      console.log('a!!')
    },
    handlerD() {
      console.log('ctrl + shift + a!!')
    }
  }
}
</script>

<style scoped>
  h1 {
    font-size: 20px;
  }
</style>>