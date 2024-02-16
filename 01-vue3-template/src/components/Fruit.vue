<template>
  <li>{{ name }}?!</li>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: ''
    }
  }
}
</script>

<!-- scoped는 유효 범위 잡기 -->
<style scoped lang="scss"> 
  h1 {
    color:red !important;
  }
</style>