<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <el-row>
          <el-col :span="3">
            <div class="grid-content bg-purple">
              <el-input placeholder="搜索用户名" prefix-icon="el-icon-search"></el-input>
            </div>
          </el-col>
          <el-col :span="3">
            <div class="grid-content bg-purple">
              <el-dropdown>
                <el-button>
                  请选择分组区域
                  <i class="el-icon-arrow-down el-icon--right"></i>
                </el-button>
                <el-dropdown-menu slot="dropdown"></el-dropdown-menu>
              </el-dropdown>
            </div>
          </el-col>
          <el-col :span="3">
            <div class="grid-content bg-purple-light">
              <el-dropdown>
                <el-button>
                  请选择小组名称
                  <i class="el-icon-arrow-down el-icon--right"></i>
                </el-button>
                <el-dropdown-menu slot="dropdown"></el-dropdown-menu>
              </el-dropdown>
            </div>
          </el-col>
          <el-col :span="3">
            <div class="grid-content bg-purple">
              <el-dropdown>
                <el-button>
                  请选择角色名称
                  <i class="el-icon-arrow-down el-icon--right"></i>
                </el-button>
                <el-dropdown-menu slot="dropdown"></el-dropdown-menu>
              </el-dropdown>
            </div>
          </el-col>
          <el-col :span="5">
            <div class="grid-content bg-purple-light">
              <div class="block">
                <el-date-picker v-model="value1" type="date" placeholder="请选择创建时间"></el-date-picker>
              </div>
            </div>
          </el-col>
          <el-col :span="3">
            <div class="grid-content bg-purple">
              <el-button type="primary">查询</el-button>
            </div>
          </el-col>
          <el-col :span="1">
            <div class="grid-content bg-purple-light">
              <el-button type="primary">添加用户</el-button>
            </div>
          </el-col>
        </el-row>
        <div class="content">
          <el-table :data="tableData" style="width: 100%">
            <el-table-column prop="SheBei" label="分组区域"></el-table-column>
            <el-table-column prop="xl" label="小组名称"></el-table-column>
            <el-table-column prop="dqz" label="角色名称"></el-table-column>
            <el-table-column prop="cjd" label="创建时间"></el-table-column>
            <el-table-column prop="SunDian" label="备注"></el-table-column>
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
    </el-card>
  </d2-container>
</template>

<script>
export default {
  name: 'yhgroup',
  data () {
    return {
      searchForm: {
        page: 1,
        per_page: 10
      },
      tot: 0,
      value1: '',
      currentPage: 5,
      tableData: [
        {
          SheBei: 'xxxx',
          xl: 'xxxx',
          dqz: 'xxxx',
          cjd: 'xxxx',
          SunDian: 'xxxx'
        },
        {
          SheBei: 'xxxx',
          xl: 'xxxx',
          dqz: 'xxxx',
          cjd: 'xxxx',
          SunDian: 'xxxx'
        }
      ]
    }
  },
  methods: {
    handleSizeChange () {},
    handleCurrentChange () {}
  }
}
</script>
 <style lang="scss" scoped>
.el-col {
  margin: 0;
  padding: 0;
  margin-right: 10px;
}
.el-pagination {
  text-align: center;
}
.el-button {
  width: 150px;
}
</style>
