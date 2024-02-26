<template>
  <span @click="increase">{{ count }}</span>
</template>

<script>
export default {
  data() {
    return { count: 0 }
  },
  methods: {
    increase () {
      this.count++;
    }
  }
}
</script>

<style>
  span {
    font-size: 50px;
    cursor: pointer;
  }
</style>