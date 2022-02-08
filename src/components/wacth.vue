<template>
  <div>
    <span>{{sum}}</span>
    <button @click="sum++">+1</button>

    <hr>

    <div>当前的信息:{{msg}}</div>
     <button @click="msg+='!'">+1</button>
  </div>
</template>

<script>
import {ref,watch} from "vue"
export default {
  setup () {
    
    let sum = ref(0)
    let msg = ref('你好')

    // 监视
    // watch(sum,(newArr,oldArr)=>{
    //   console.log('sum变换了',newArr,oldArr);
    // })
    //   watch(msg,(newArr,oldArr)=>{
    //   console.log('msg变换了',newArr,oldArr);
    // })
      watch([msg,sum],(newArr,oldArr)=>{
      console.log('msg变换了',newArr,oldArr);
    },{
      inmediate:true
    })
    return {
      sum,
      msg
    }
  }
}
</script>

<style lang="scss" scoped>

</style>