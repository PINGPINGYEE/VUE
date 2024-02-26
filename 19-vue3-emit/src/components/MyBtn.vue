<template>
  <div class="btn">
    <slot></slot>
  </div>
  <!-- <h1></h1> --> <!-- 요소를 하나 더 만들면 상속이 안됨 -->
  <h1 @dblclick="$emit('listener', 'doubleClick'+$event)">
    ABC</h1> <!-- dblclick은 더블 클릭 + 매개변수의 , 뒤에는 이벤트가 실행될 떄 데이터 + $는 이벤트 객체를 데이터로 전달 -->
  <input type="text" v-model="msg" />
</template>

<script>
export default {
  // inheritAttrs: false // app.vue에서 작성한 내용이 상속 안되게 함

  // emits를 사용하면 요소에 직접 할당 가능하여 요소가 여러개여도 됨
  emits: [
    'listener',
    'changeMsg'
  ],
  data () {
    return {
      msg: ''
    }
  },
  watch: {
    msg() {
      this.$emit('changeMsg', this.msg) // 두번째 인자는 데이터
    }
  }
}
</script>

<style scoped>
  .btn {
    display: inline-block;
    margin: 4px;
    padding: 6px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  }
</style>