<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <el-table
      ref="multipleTable"
      :data="cjList"
      tooltip-effect="dark"
      style="width: 100%"
      @selection-change="handleSelectionChange"
    >
      <el-table-column type="selection" width="55"></el-table-column>
      <el-table-column prop="cjName" label="采集点名称" width="160"></el-table-column>
      <el-table-column prop="sbName" label="所属设备名称" width="160"></el-table-column>
      <el-table-column prop="xlName" label="所属线路名称" width="160"></el-table-column>
      <el-table-column prop="sDabc" label="实时湿度ABC" width="160"></el-table-column>
      <el-table-column prop="sunD" label="太阳能电压" width="160"></el-table-column>
      <el-table-column prop="dcdy" label="电池电压" width="160"></el-table-column>
      <el-table-column prop="cjTime" label="采集时间" width="160"></el-table-column>
      <el-table-column label="操作" width="160">
        <i class="el-icon-view" @click="handleEdit()"></i>
        <i class="el-icon-delete" @click="handleDelete()"></i>
      </el-table-column>
    </el-table>
    <div class="footer">
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
  name: 'sbpoint',
  data () {
    return {
      cjList: [
        {
          cjName: 'xx',
          sbName: 'xx',
          xlName: 'xx',
          sDabc: 'xx',
          sunD: 'xx',
          dcdy: 'xx',
          cjTime: 'xx'
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
    handleSelectionChange (val) {
      this.multipleSelection = val
    },
    handleSizeChange () {},
    handleCurrentChange () {},
    handleEdit () {},
    handleDelete () {}
  }
}
</script>
<style lang="scss" scoped>
.el-icon-view {
  margin-right: 20px;
}
.footer {
  margin-top: 20px;
}
.el-pagination {
  text-align: center;
}
</style>
