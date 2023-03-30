<template>
  <el-button type="success">姓名：{{name}}</el-button>
  <el-button type="warning">年龄：{{age}}</el-button>
</template>

<script setup>
defineProps({
  name: String,
  age: Number
})
</script>

<style scoped>

</style>