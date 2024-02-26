<template>
  <h1>{{ count }}</h1>
</template>

<script>
export default {
  data() {
    return {
      count: 2
    }
  },
  // 비교를 위해 실제 실행 순서 역순으로 작성
  mounted() {
    console.log('Mounted!', this.count);
    console.log(document.querySelector('h1'))
  },
  beforeMount() {
    console.log('Before Mount!', this.count)
    console.log(document.querySelector('h1'))
  },
  created() {
    console.log('Created!', this.count);
    console.log(document.querySelector('h1'))
  },
  beforeCreate() {
    console.log('Before Create!', this.count)
    console.log(document.querySelector('h1'))
  }
}
</script>
