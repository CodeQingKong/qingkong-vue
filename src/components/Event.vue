<template>
  <div class="box1" @click="clickHandler('box1')">
      box1
      <div class="box2" @click.stop="clickHandler('box2')">
          box2
          <div class="box3" @click.stop="clickHandler('box3')">
              box3
          </div>
      </div>
  </div>
</template>

<script setup>
// 事件冒泡
function clickHandler(text){
    alert(text);
}
</script>

<style scoped>
.box1{
    height: 200px;
    width: 200px;
    background: green;
}
.box2{
    height: 100px;
    width: 100px;
    background: aquamarine;
}
.box3{
    height: 50px;
    width: 50px;
    background: orange;
}
</style>