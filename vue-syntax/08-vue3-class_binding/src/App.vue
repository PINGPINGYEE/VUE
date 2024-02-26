<template>
  <!-- :class같은 경우 v-bind:를 생략하고 :만 사용(약어) -->
  <h1
  :class="{activate: isActivate}" 
  @click="activate"> <!-- isActivate가 true인 경우에만 activate 클래스 사용 -->
    Hello?!({{ isActivate }})
  </h1>
</template>

<script>
export default {
  data() {
    return {
      isActivate: false
    }
  },
  methods: {
    activate() {
      this.isActivate = true
    }
  }
}
</script>

<style scoped>
  .activate {
    color: red;
    font-weight: bold;
  }
</style>