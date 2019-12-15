<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <div class="kz">
      <el-button type="primary" icon="el-icon-search">登录</el-button>
      <el-button type="primary" icon="el-icon-thumb">操作</el-button>
      <el-button type="primary" icon="el-icon-search">预警</el-button>
    </div>
    <div class="content">
          <el-table :data="tableData" style="width: 100%" >
            <el-table-column prop="bh" label="编号" ></el-table-column>
            <el-table-column prop="us" label="用户/设备"></el-table-column>
            <el-table-column prop="time" label="时间"></el-table-column>
            <el-table-column prop="cont" label="内容"></el-table-column>
            <el-table-column prop="dizhi" label="IP地址"></el-table-column>
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
  </d2-container>
</template>

<script>
export default {
  name: 'xtlog',
  data () {
    return {
      searchForm: {
        page: 1,
        per_page: 10
      },
      tot: 0,
      value1: '',
      currentPage: 5,
      tableData: [{
        bh: 'xxxx',
        us: 'xxxx',
        time: 'xxxx',
        cont: 'xxxx',
        dizhi: 'xxxx'
      }]
    }
  },
  methods: {
    handleSizeChange () {},
    handleCurrentChange () {}
  }
}
</script>
<style llang="scss" scoped>
.kz {
  margin-left: 70%;
}
.el-pagination {
  text-align: center;
  margin-top: 15px;
}
</style>
