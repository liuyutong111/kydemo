<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <div class="header">
      <el-col :span="3">
        <div class="grid-content bg-purple">
          <el-input placeholder="搜索关键字" prefix-icon="el-icon-search"></el-input>
        </div>
      </el-col>
      <div class="fr">
        <el-button type="primary">添加采集点</el-button>
        <el-button type="primary">添加线路</el-button>
      </div>
      <div class="content">
        <el-table :data="xlList" style="width: 100%">
         <el-table-column prop="lineName" label="线路名称"></el-table-column>
            <el-table-column prop="sb" label="所属设备"></el-table-column>
            <el-table-column prop="cj" label="采集点"></el-table-column>
          <el-table-column  label="操作">
            <i class="el-icon-edit" @click="handleEdit()"></i>
            <i class="el-icon-delete" @click="handleDelete()"></i>
          </el-table-column>
        </el-table>
      </div>
      <el-pagination
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
        :current-page="searchForm.page"
        :page-sizes="[10, 15, 20, 40]"
        :page-size="searchForm.per_page"
        layout="total, sizes, prev, pager, next, jumper"
        :total="tot"
        background
      ></el-pagination>
    </div>
  </d2-container>
</template>

<script>
export default {
  name: 'bjlinelist',
  data () {
    return {
      xlList: [
        {
          lineName: 'xxxx',
          sb: 'xxxx',
          cj: 'xxxx'
        }
      ],
      searchForm: {
        page: 1,
        per_page: 10
      },
      tot: 0,
      value1: '',
      currentPage: 5
    }
  },
  methods: {
    handleSizeChange () {},
    handleCurrentChange () {},
    handleEdit () {},
    handleDelete () {}
  }
}
</script>
<style lang="scss" scoped>
.header {
  width: 100%;
  height: 40px;
  .fr {
    float: right;
  }
}
.el-table {
  margin-top: 30px;
}
 .el-icon-edit {
    margin-right: 20px;
  }
.el-pagination {
  text-align: center;
  margin-top: 20px;
}
</style>
