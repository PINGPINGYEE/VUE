<template> <!-- 최상위 태그에는 v-if를 사용할 수 없음 -->
  <button @click="handler">
    Click me!
  </button>
  <!-- <h1 v-if="isShow">Hello?!</h1>
  <h1 v-else-if="count > 3">Count > 3</h1>
  <h1 v-else>Good~</h1> -->
  <template v-if="isShow"> <!-- div를 쓰면 div로 감싸져있지만 template을 쓰면 감싸져있지 않음(template은 따로 렌더링이 되지 않음) -->
    <!-- <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p> -->
  </template>
  <h1 v-show="isShow">Hello?!</h1> <!-- h1 요소는 보여지지만(렌더링) style에 display가 none으로 되어 있음 + template 요소는 사용 불가 -->
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
      count: 0
    }
  },
  methods: {
    handler() {
      this.isShow = !this.isShow,
      this.count++
    }
  }
}
</script>