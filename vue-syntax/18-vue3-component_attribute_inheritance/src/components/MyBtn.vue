<template>
  <div class="btn">
    <slot></slot>
  </div>
  <div></div> <!-- div(요소)를 한개 더 생성 시 App.vue에서 선언한 class가 사라짐(어떤 자식 요소에게 줘야하는지 모르기 때문) + style 요소도 같은 원리로 적용 안됨 -->
  
  <h1 :class="$attrs.class"
      :style="$attrs.class"></h1>
  <h1 v-bind="$attrs"></h1>
</template>

<script>
export default {
  inheritAttrs: false, // 최상위 요소가 하나만 있을때도 기본적인 속성의 내용들을 상속하지 않겠다라고 선언하는 것
  created() {
    console.log(this.$attrs)
  }
}
</script>

<style scoped>
  .btn {
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  }
</style>