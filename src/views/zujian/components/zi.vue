<template>
  <div>
    我是子组件{{ arr }}
    <!-- <el-button @click="an">按钮</el-button> -->
    <el-button @click="an">按钮</el-button>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  props: {
    arr: {
      type: Array,
      default: function () {
        return []
      },
    },
  },
  // methods:{
  //   an(){
  //     let src ={
  //       a:123,
  //       b:234
  //     }
  //     this.$parent.add(src)
  //   }
  // }
  methods:{
    an(){
      this.$parent.add(123)
    }
  }
}
</script>

<style >
</style>