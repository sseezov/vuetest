<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button",
};
</script>

<style scoped>
.btn {
  margin-top: 5px;
  margin-bottom: 5px;
  padding: 10px;
  float: right;
  background: none;
  border: 1px solid teal;
  cursor: pointer;
}
</style>
