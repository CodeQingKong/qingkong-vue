<template xmlns="http://www.w3.org/1999/html">
<!--  <el-text type="danger" v-show="isNameShow">姓名：{{ obj.name }}</el-text>-->
<!--  <br>-->
<!--  <el-text type="danger" v-show="isAgeShow">年龄：{{ obj.age }}</el-text>-->
<!--  <br>-->
<!--  <el-button type="success" @click="increment">count++：{{ count }}</el-button>-->
  <hello v-for="player in array" :name=player.name :age=player.age></hello>
</template>

<script setup>
import {ref, reactive, computed} from "vue";
import Hello from "@/components/Hello.vue";

const count = ref(0)
const obj = reactive({
  name: "Logan Luo",
  age: "24"
})

const isNameShow = computed(() => {
  return count.value >= 2
})
const isAgeShow = computed(() => {
  return count.value >= 1
})

const array = [
  {
    name: "梅西",
    age: 32
  },
  {
    name: "C罗",
    age: 38
  },
  {
    name: "内马尔",
    age: 36
  }
]

function increment() {
  count.value++;
}
</script>

<style scoped>
</style>