<template>
  <button @click="handler">click me</button>
  <ul>
    <li
    v-for="(fruit, index) in fruits"
    :key="fruit"
    >
      {{ fruit }}-{{ index + 1 }}
    </li>
    <li
    v-for="{id, name} in newFruits"
    :key="id"
    >
      {{ name }}-{{ id }}
    </li>
  </ul>
</template>

<script>
import shortid from 'shortid' // shortid는 고유한 id를 만들어주는 패키지 + shortid 패키지를 터미널을 통해 설치 (npm i -D shortid)

export default {
  data() {
    return {
      fruits: ['Apple', 'Banana', 'Cherry'],
      // newFruits: [{id: 0, name: 'Apple'}, {id: 1, name: 'Banana'}, {id: 0, name: 'Cherry'}] -> newFruits의 객체 배열 예시
    }
  },
  computed: {
    // 원래 형태
    // newFruits() {
    //   return this.fruits.map((fruit, index)=>{
    //     return {
    //       id: index,
    //       name: fruit
    //     }
    //   })
    // },

    // shortid 패키지 사용
    newFruits() {
      return this.fruits.map(fruit => ({
        id: shortid.generate(),
        name: fruit
      }))
    },
  },
  methods: {
    handler() {
      this.fruits.push('Orange')
    }
  }
}
</script>