<!--
  -- 약어 --
  v-bind: => :
  v-on: => @
  v-slot: => #
-->

<template>
  <MyBtn>
    <template #text>
      <span>Banana</span>
    </template>
    <template #icon>
      <span>(B)</span> <!-- 아이콘이라고 가정 -->
    </template>
  </MyBtn>
</template>

<script>
  import MyBtn from './components/MyBtn.vue'

  export default {
    components: {
      MyBtn
    }
  }

</script>