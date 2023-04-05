<template>
  <el-button type="success">{{success}}</el-button>
  <el-button type="warning">{{warning}}</el-button>
  <br>
  <br>
</template>

<script setup>
  defineProps({
      success: String,
      warning: String
  })
</script>

<style scoped>

</style>