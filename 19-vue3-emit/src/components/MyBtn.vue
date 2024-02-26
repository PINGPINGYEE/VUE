<template>
  <div class="btn">
    <slot></slot>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
  .btn {
    display: inline-block;
    margin: 4px;
    padding: 6px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  }
</style>