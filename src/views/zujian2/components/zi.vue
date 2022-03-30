<template>
  <div>我是子组件 {{arr}}
    <el-button @click="anniu">按钮</el-button>
  </div>
 
</template>

<script>
export default {
name:"Zi",
data(){
    return{

    }
},
props:{
    arr:{
        type:Array,
        default(){
            return []
        }
    }
},
methods:{
    anniu(){
        this.$parent.add(123)
    }
}
}
</script>

<style>

</style>