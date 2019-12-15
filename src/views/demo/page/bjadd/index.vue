<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <div class="alarm_name">
     <el-row :gutter="20">
        <el-col :span="18"><div class="grid-content bg-purple"></div></el-col>
        <el-col :span="6"><div class="grid-content bg-purple alarm_username">
          <el-input v-model="input" placeholder="请输入内容"></el-input>
           <el-button type="primary">查询</el-button>
            <el-button type="primary">添加</el-button>
          </div></el-col>
        
     </el-row>
    </div>
      <el-table
    :data="tableData"
    tooltip-effect="dark"
    style="width: 100%"
  >
    <!-- <el-table-column
      type="selection"
       align="center"
     >
    </el-table-column> -->
    <el-table-column
      label="姓名"
      align="center"
      >
      <template slot-scope="scope">{{ scope.row.date }}</template>
    </el-table-column>
    <el-table-column
      prop="name"
      label="手机号"
      align="center"
      width="150">
    </el-table-column>
    <el-table-column
      prop="address"
      label="邮箱"
      align="center"
      show-overflow-tooltip>
    </el-table-column>
    <el-table-column
      prop="Processing"
      label="微信"
      align="center"
      show-overflow-tooltip>
    </el-table-column>
    <el-table-column
      prop="state_time"
      align="center"
      label="备注"
      show-overflow-tooltip>
    </el-table-column>
     <el-table-column
      label="操作"
      width="100">
      <template slot-scope="scope">
        <el-button @click="handleClick(scope.row)" type="text" size="small">编辑</el-button>
        <el-button type="text" size="small" @click="open">删除</el-button>
      </template>
    </el-table-column>
  </el-table>
  <div class="block">
    <el-pagination
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
      :current-page="currentPage4"
      
      :page-size="100"
      layout=" prev,  pager, next,sizes, jumper"
      :page-sizes="[100, 200, 300, 400]"
      background
      :total="400">
    </el-pagination>
  </div>
  </d2-container>
</template>

<script>
export default {
  name: 'bjadd',
  data() {
      return {
        currentPage4:4,
        input:'',
        tableData: [{
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄',
          Processing:'已处理',
          state_time:'2019-12-13',
        }, {
          date: '2016-05-02',
          name: '王小虎',
           address: '上海市普陀区金沙江路 1518 弄',
          Processing:'已处理',
          state_time:'2019-12-13',
        }, {
          date: '2016-05-04',
          name: '王小虎',
           address: '上海市普陀区金沙江路 1518 弄',
          Processing:'已处理',
          state_time:'2019-12-13',
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄',
          Processing:'已处理',
          state_time:'2019-12-13',
        }, {
          date: '2016-05-08',
          name: '王小虎',
           address: '上海市普陀区金沙江路 1518 弄',
          Processing:'已处理',
          state_time:'2019-12-13',
        }, {
          date: '2016-05-06',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄',
          Processing:'已处理',
          state_time:'2019-12-13',
        }, {
          date: '2016-05-07',
          name: '王小虎',
           address: '上海市普陀区金沙江路 1518 弄',
          Processing:'已处理',
          state_time:'2019-12-13',
        }],
        multipleSelection: []
      }
    },

    methods: {
      // 多选框
      // toggleSelection(rows) {
      //   if (rows) {
      //     rows.forEach(row => {
      //       this.$refs.multipleTable.toggleRowSelection(row);
      //     });
      //   } else {
      //     this.$refs.multipleTable.clearSelection();
      //   }
      // },
      // handleSelectionChange(val) {
      //   this.multipleSelection = val;
      // },
       handleClick(row) {
        console.log(row);
      },
      //删除
      open() {
        this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
          type: 'warning',
          center: true
        }).then(() => {
          this.$message({
            type: 'success',
            message: '删除成功!'
          });
        }).catch(() => {
          this.$message({
            type: 'info',
            message: '已取消删除'
          });
        });
      },
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
    
    }
}
</script>
<style>
 .block{
   text-align: center;
   padding:40px 0;
   background: #fff;
 }
 .block .el-input__inner{
   color:#666;
   margin-left: 0px;
 }
 .alarm_name{
   padding-bottom: 20px;
 }
 .alarm_username .el-input{
    width:auto;
    border: 1px solid #ddd;
    margin-right: 20px;
  }
</style>
 
 