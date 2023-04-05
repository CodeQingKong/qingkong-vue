<template xmlns="http://www.w3.org/1999/html">
    <!--  自定义事件 -->
    <CustomEvent :students=students @delete-event=deleteStudentHandler @create-event="createStudentHandler"></CustomEvent>
</template>

<script setup>
import CustomEvent from "@/components/CustomEvent.vue";
import {reactive} from "vue";
const students = reactive([
    {
        id: 1,
        name: "孙悟空",
        age: 18,
        gender: '男',
        address: "花果山"
    },
    {
        id: 2,
        name: "猪八戒",
        age: 28,
        gender: '男',
        address: "高老庄"
    },
    {
        id: 3,
        name: "沙和尚",
        age: 38,
        gender: '男',
        address: "流沙河"
    },
    {
        id: 4,
        name: "唐三藏",
        age: 16,
        gender: '男',
        address: "大唐"
    }
])
function deleteStudentHandler(index) {
    students.splice(index, 1);
    console.log("删除学生")
}

function createStudentHandler(student) {
    const lastId = students[students.length - 1].id;
    student.id = !isNaN(lastId) ? lastId + 1 : 1;
    students.push(student);
}
</script>

<style scoped>
</style>