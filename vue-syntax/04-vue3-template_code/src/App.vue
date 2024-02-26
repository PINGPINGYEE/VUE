<template>
  <h1 v-once @click="add">{{ msg }}</h1> <!-- v-once: 최초 한번의 렌더링 이후에는 데이터의 수정과 상관없이 화면을 갱신하지 않음(반응성을 가지지 않음) + @[조건]은 v-on:[조건]=""의 약어-->
  <h1 v-html="msgHtml"></h1> <!-- 원시 HTML 사용 -->
  <h1 :class="msgWithClass">{{ msgWithClass }}</h1> <!-- HTML 속성 사용(원래 형태는 v-bind:[속성]="") -->
  <h1 :[attr]="msgWithClass" @[event]="add">{{ msgWithClass }}</h1> <!-- 동적 인자 사용 + attr은 attribute(속성)라는 뜻 -->
  <h1 :[attr]="`active`" @[event]="add">{{ msgWithClass }}</h1> <!-- msgWithClass 변수에 !가 계속 추가되기에 css 클래스와 달라져 직접 `active`라는 클래스의 이름을 입력 -->
</template>

<script>
export default {
  data() {
    return {
      msg: 'Hello world!',
      msgHtml: '<div style="red;">Hello!!</div>',
      msgWithClass: 'active',
      attr: 'class',
      event: 'click',
      msgWithArg: 'Hello world!'
    }
  },
  methods: {
    add() {
      this.msg += '!'
      this.msgWithClass += '!'
    }
  }
}
</script>

<style>
  .active {
    color: royalblue;
    font-size: 100px;
  }
</style>