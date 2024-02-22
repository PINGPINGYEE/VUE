<template>
  <h1>no.1</h1>
  <MyBtn />
  <h1>no.2</h1>
  <MyBtn text="Banana"/>
  <h1>no.3</h1>
  <MyBtn>Banana</MyBtn>
  <h1>no.4</h1>
  <MyBtn color="royalblue"/>
  <h1>no.5</h1>
  <MyBtn :color="123"/> <!-- 다음과 같이 바인딩을 해야 숫자로 인식(설정해 둔 type 때문에) -> 어차피 에러 -->
  <h1>no.6</h1>
  <MyBtn color="#000"/>
  <h1>no.7</h1>
  <MyBtn :color="color"/>
  <h1>no.8</h1>
  <MyBtn large color="royalblue"/>
  <h1>no.9</h1>
  <MyBtn :color="color"><span style="color: red;">Banana</span></MyBtn>
  <br>
  <button>Banana</button>
</template>

<script>
import MyBtn from './components/MyBtn.vue'

export default {
  components: {
    MyBtn
  },
  data() {
    return {
      color: '#000'
    }
  }
}
</script>

<style>
  h1 {
    font-size: 15px;
  }
</style>