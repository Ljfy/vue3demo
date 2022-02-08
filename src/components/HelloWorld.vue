<template>
  <div>

    <h1>一个人的个人信息</h1>
    姓: <input type="text" v-model="person.firstName">
    名: <input type="text" v-model="person.lastName">
    <br>

    <span>全名:{{person.fullName}}</span>
  </div>
</template>

<script>
//reactive
import {computed,reactive} from "vue"
export default {
  setup () {
    // 数据 
    let person = reactive({
      firstName:"张",
      lastName:'三'
    })

    // 计算属性 简写(没有考虑计算属性被修改的情况)
    // person.fullName = computed(()=>{
    //   return person.firstName + '-'+person.lastName
    // })

    // 完整写法 考虑读和写
     person.fullName = computed({
       get(){
         return person.firstName + '-'+person.lastName
       },
       set(value){
         const nameArr = value.split('-')
         person.firstName = nameArr[0]
         person.lastName = nameArr[1]
       }
     })
    return{
      person,
      
    }
  }
 }

</script>

<style lang="scss" scoped>

</style>