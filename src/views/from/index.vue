<template>
  <div>
    <el-button type="primary" @click="add">新增</el-button>
    <el-table :data="tableData" border style="width: 50%">
      <el-table-column prop="date" label="日期" width="180"> </el-table-column>
      <el-table-column prop="name" label="姓名" width="180"> </el-table-column>
      <el-table-column prop="address" label="地址"> </el-table-column>
      <el-table-column fixed="right" label="操作" width="150">
        <template slot-scope="scope">
          <el-button type="text" size="small" @click="handleel(scope.row)"
            >删除</el-button
          >
          <el-button type="text" size="small">查看</el-button>
          <el-button type="text" size="small" @click="handleClick(scope.row)"
            >编辑</el-button
          >
        </template>
      </el-table-column>
    </el-table>
    <log :dialogVisible="dialogVisible" :item="item"></log>
    <addlog :dialogVisibles="dialogVisibles"></addlog>
  </div>
</template>

<script>
import log from "./components/log.vue";
import addlog from "./components/addlog.vue";
export default {
  name: "From",
  components: {
    log,
    addlog,
  },
  data() {
    return {
      tableData: [
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄",
        },
        {
          date: "2016-05-04",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄",
        },
        {
          date: "2016-05-01",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1519 弄",
        },
        {
          date: "2016-05-03",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1516 弄",
        },
      ],
      dialogVisible: false,
      dialogVisibles: false,
      item: {},
    };
  },
  methods: {
    //编辑、查看
    handleClick(row) {
      this.dialogVisible = true;
      this.item = row;
    },
    //删除
    handleel() {
      this.$alert("是否确定删除", "标题名称", {
        confirmButtonText: "确定",
        callback: (action) => {
          // 调接口

          this.$message({
            type: "info",
            message: `删除成功 ${action}`,
          });
        },
      });
    },
    //新增
    add() {
      this.dialogVisibles = true;
    },

    //编辑取消
    guan() {
      this.dialogVisible = false;
      this.dialogVisibles = false;
    },
    //编辑确定
    qadd(from) {
      //调接口
      //    zhen
      console.log(from);
      this.dialogVisible = false;
    },
  },
};
</script>

<style>
</style>