<template>
    <el-table :data=students>
        <el-table-column prop="id" label="id"/>
        <el-table-column prop="name" label="姓名"/>
        <el-table-column prop="age" label="年龄"/>
        <el-table-column prop="gender" label="性别"/>
        <el-table-column prop="address" label="住址"/>
        <el-table-column label="操作">
            <template #default>
                <el-button link type="danger" size="small" @click='deleteEventHandler(1)'>删除</el-button>
            </template>
        </el-table-column>
    </el-table>
    <hr/>
    <el-form class="create-form">
        <el-form-item label="姓名">
            <el-input v-model="student.name"/>
        </el-form-item>
        <el-form-item label="年龄">
            <el-input v-model="student.age" type="number"/>
        </el-form-item>
        <el-form-item label="性别">
            <el-select v-model="student.gender" placeholder="请选择性别" style="width: 300px">
                <el-option label="男" value="男"/>
                <el-option label="女" value="女"/>
            </el-select>
        </el-form-item>
        <el-form-item label="住址">
            <el-input v-model="student.address"/>
        </el-form-item>
        <el-form-item>
            <el-button type="primary" @click="createEventHandler(student)">创建</el-button>
        </el-form-item>
    </el-form>
</template>

<script setup>
// 自定义事件
import {reactive} from "vue";
const customEvent = defineEmits(['delete-event','create-event']);
function deleteEventHandler(index){
    customEvent('delete-event',index)
}
function createEventHandler(student){
    customEvent('create-event',Object.assign({},student))
}
defineProps(['students'])
const student = reactive({
    id: null,
    name: '',
    age: null,
    gender: '',
    address: ''
})
</script>

<style scoped>
.create-form{
    width: 300px;
}
</style>