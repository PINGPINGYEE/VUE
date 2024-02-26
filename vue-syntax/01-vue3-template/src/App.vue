<!-- HTML -->
<template>
  <h1 @click="increase">
  {{ count }} <!-- JS에서 count 불러오기(반응성(Reactivity): 데이터를 갱신하면 화면도 바뀜) -->
  </h1>
  <div v-if="count > 4">
    4보다 큽니다!
  </div>
  <ul>
    <Fruit
      v-for="fruit in fruits"
      :key="fruit"
      :name="fruit"> <!-- 고유한 지 체크를 위해 key를 생성 -->
      {{ fruit }}
    </Fruit>
  </ul>
</template>

<!-- JS -->
<script>
import Fruit from '~/components/Fruit'
export default {
  components: {
    Fruit
  },
  data() { // data: function() {}이랑 동일
    return {
      count: 0,
      fruits: ['apple', 'banana', 'cherry']
    }
  },
  methods: {
    increase() {
      this.count += 1;
    }
  }
}
</script>

<!-- CSS -->
<style lang="scss">
  h1 {
    font-size:50px;
    color:royalblue;
  }
  ul {
    li {
      font-size: 40px;
    }
  }
</style>