<template>
  <h1>prevent</h1>
  <a href="https://naver.com" target="_blank" @click="handler1">NAVER</a> <!-- target="_blank"는 새로운 탭에서 네이버를 열게 해주는 것 -->
  <br>
  <a href="https://naver.com" target="_blank" @click.prevent="handler2">NAVER</a> <!-- prevent 수식어로 preventDefault()를 단순화 -->
  <br>
  <h1>once</h1>
  <a href="https://naver.com" target="_blank" @click.once="handler2">NAVER</a> <!-- 특정 이벤트가 발생했을때 해등하는 메소드를 단 한번만 실행해주는 개념 -->
  <br>
  <h1>prevent.once</h1>
  <a href="https://naver.com" target="_blank" @click.prevent.once="handler2">NAVER</a> <!-- chaining 형태로 붙여서 여러 개를 사용 -->
  <br>
  <h1>stop</h1>
  <div class="parent" @click="handlerA">
    <div class="child1" @click="handlerB"></div>
    <div class="child2" @click.stop="handlerC"></div> <!-- stop의 수식어로 stopPropagation()를 단순화 -->
  </div>
  <h1>capturing</h1>
  <div class="parent" @click.capture="handlerAA"> <!-- 해당하는 내용이 반대로 동작하도록 함(parent 먼저 동작한 후 child 동작) -->
    <div class="child" @click="handlerAB"></div>
  </div>
  <h1>capture.stop</h1>
  <div class="parent" @click.capture.stop="handlerAA"> <!-- 해당하는 내용이 반대로 동작하도록 함(parent 먼저 동작한 후 child 동작) -->
    <div class="child" @click="handlerAB"></div>
  </div>
  <h1>self</h1>
  <div class="parent" @click.self="handlerBA"> <!-- self라는 수식어가 붙어있는 그 클릭이라는 이벤트가 붙어있는 영역을 정확하게 클릭을 했을때 해당하는 이벤트가 동작 -->
    <div class="child"></div>
  </div>
  <h1>target&amp;currentTarget</h1>
  <div class="parent" @click="handlerCA">  <!-- self는 target과 currentTarget이 같을때 메소드가 동작을 하게 함 -->
    <div class="child"></div>
  </div>
  <h1>passive</h1>
  <div class="parentA" @wheel.passive="handlerDA"> <!-- JS의 로직의 처리와 화면의 스크롤을 독립시켜줌 -->
    <div class="childA"></div>
  </div>
</template>

<script>
export default {
  methods: {
    handler1(event) {
      event.preventDefault() // 기본 동작을 방지(html에 기본적으로 있는 기능인 건데 그 내용을 동작시키지 않고 단순하게 메소드만 실행하겠다는 개념)
      console.log('ABC!')
    },
    handler2() {
      console.log('ABC!')
    },
    handlerA() { // child를 클릭하는 것은 parent를 클릭하는 것과 동일하기에 child를 눌러도 출력 -> 이벤트 버블링(거품이 일어나듯이 계속 확산)
      console.log('A')
    },
    handlerB(event) {
      event.stopPropagation() // 이벤트가 전파되는 것을 방지(이벤트 버블링 방지)
      console.log('B')
    },
    handlerC() {
      console.log('C')
    },
    handlerAA() {
      console.log('A')
    },
    handlerAB() {
      console.log('B')
    },
    handlerBA(){
      console.log('A')
    },
    handlerCA(event) {
      console.log(event.target)
      console.log(event.currentTarget)
      console.log('A')
    },
    handlerDA(event) {
      for(let i = 0; i < 10000; i++) console.log(event) // 부하 걸기
    }
  }
}
</script>

<style scoped>
  h1 {
    font-size: 20px;
  }

  div {
    display: flex;
  }
  .parent {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
  }

  .parent .child{
    width: 100px;
    height: 100px;
    background-color: orange;
  }

  .parent .child1{
    width: 100px;
    height: 100px;
    margin: 5px;
    background-color: orange;
  }

  .parent .child2{
    width: 100px;
    height: 100px;
    margin: 5px;
    background-color: orange;
  }

  .parentA {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    overflow: auto; /* 안에 있는 요소의 내용이 parent보다 넘치는 구조를 가지고 있으면 스크롤바를 생성 */
  }

  .parentA .childA {
    width: 100px;
    height: 2000px;
    background-color: orange;
  }
</style>