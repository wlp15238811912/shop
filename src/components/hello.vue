<template>
    <div>
        <el-form :model="data" ref="data" label-width="100px">
            <el-form-item v-for="(item, index) in data.list" label="姓名"
                :prop="'list.'+index+'.name'" :rules="{
                  required: true, message: '名字不能为空', trigger: 'blur'
                }">
                <el-input v-model="item.name"></el-input>
            </el-form-item>
            <el-button @click.prevent="add()">添加</el-button>
            </el-form>
            <img :src="logo" alt="">
    </div>
</template>
<script>
export default {
    data() {
        return {
            data:{
                list:[
                    {
                        name:'',
                        age:''
                    }
                ]
            },
            logo:require('@/assets/logo.png')
        }
    },
    created() {
    },
    computed: {
    },
    methods: {
        add(){
            this.data.list.push({
                name:'',
                age:''
            })
        }
    },
}
</script>
<style lang="scss" scoped>

</style>
