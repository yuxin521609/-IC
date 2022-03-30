<template>
  <div>

<el-dialog
  title="提示"
  :visible.sync="dialogVisible"
  width="30%"
  >
  <span>
      {{item.name}}

  </span>
  <span slot="footer" class="dialog-footer">
    <el-button @click="dialog">取 消</el-button>
    <el-button type="primary" @click="dialogadd">确 定</el-button>
  </span>
</el-dialog>
  </div>
</template>

<script>
export default {
    data() {
      return {
        // dialogVisible: false
        form:{}
      };
    },
    props:{
        dialogVisible:{
            type:Boolean,
            default:false,
        },
           item:{
            type:Object,
            default:function(){
                return {}
            },
        }
    },
    methods: {
        //取消
        dialog(){
            this.$parent.guan()
        },
        //确定
        dialogadd(){
          this.$parent.qadd(this.form)
        }
    }
}
</script>

<style>

</style>