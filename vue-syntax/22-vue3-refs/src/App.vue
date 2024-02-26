<template>
  <h1 id="hello">
    Hello world!
  </h1>
  <h1 ref="refhello">
    Hello world!
  </h1>
  <h1 ref="ref-hello">
    Hello world!
  </h1>
  <HelloComp ref="ChildHello" />
</template>

<script>
import HelloComp from './components/HelloComp'

export default {
  created() {
    console.log(this.$refs.refhello) // html과 연결이 되지 않은 상태라 사용 불가능
    console.log(this.$refs.ChildHello) // html과 연결이 되지 않은 상태라 사용 불가능
  },
  mounted() {
    const h1El = document.querySelector('#hello') // 정석적인 방법
    console.log(h1El.textContent)
    console.log(this.$refs.refhello.textContent) // refs를 사용한 방법(component가 html과 연결이 된 직후에만 사용 가능 => mounted에서 출력 가능)
    console.log(this.$refs['ref-hello'].textContent) // -이 있을 시
    console.log(this.$refs.ChildHello)
    console.log(this.$refs.ChildHello.$el)
    console.log(this.$refs.ChildHello.$refs.good)
  },
  components: {
    HelloComp
  }
}
</script>