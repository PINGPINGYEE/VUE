<template>
  <button :class="button1" @click="handler1">Click me!</button> <!-- handler1의 경우 매게변수로 event를 받게 선언되어 있으므로  @click="handler1($event)" 이렇게도 사용 가능-->
  <div>
    <button :class="button2" @click="handler2('hi', $event)">Click 1!</button> <!-- $event를 하게 되면 @ 뒤에 있는 이벤트가 들어감 -->
    <button :class="button2" @click="handler2('what', $event)">Click 2!</button>
  </div>
  <div>
    <button @click="handlerA(), handlerB()">Click me!</button> <!-- handlerA, B는 매게변수를 받지는 않지만 하나의 요소에 이벤트가 발생했을 때 실행할 메소드가 여러개라면 ()를 붙혀야 함 -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      // 클래스 이름을 문자열로 반환하는 데이터 속성
      button1: 'button1',
      button2: 'button2'
    }
  },
  methods: {
    handler1(event) {
      console.log(event)
      console.log(event.target)
      console.log(event.target.textContent)
    },
    handler2(msg, event) {
      console.log(msg)
      console.log(event)
    },
    handlerA() {
      console.log('A')
    },
    handlerB() {
      console.log('B')
    },
  }
}
</script>

<style scoped>
  .button1 {
    background-color: #0a0a23;
    color: #fff;
  }

  .button2 {
    background-color: #232323;
    color: #fff;
  }
</style>
