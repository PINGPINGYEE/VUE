<template>
  <div :class="{ large : large }" :style="{ backgroundColor: color }" class="btn">{{text}}</div>
  <div :class="{ large : large }" :style="{ backgroundColor: color }" class="btn"><slot>Apple</slot></div>
</template>

<script>
export default {
  props: { // 컴포넌트가 실행이 될 때 마치 속성처럼 받아내는 내용들을 받아줄 수 있는 내용을 정의해 주는 옵션 + 부모, 자식 간의 데이터 통신
    color: {
      type: String,
      default: 'gray'
    },
    large: {
      type: Boolean,
      default: false
    },
    text: {
      type: String,
      default: 'Apple'
    }
  }
}
</script>

<style scoped>
  .btn {
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  }

  .btn.large {
    font-size:20px;
    padding: 10px 20px;
  }
</style>