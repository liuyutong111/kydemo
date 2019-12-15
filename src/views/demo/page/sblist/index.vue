<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <el-row>
          <el-col :span="4">
            <div class="grid-content bg-purple">
              <el-input placeholder="搜索用户名" prefix-icon="el-icon-search"></el-input>
            </div>
          </el-col>
          <el-col :span="4">
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
          <el-col :span="4">
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
          <el-col :span="4">
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
          <el-col :span="4">
            <div class="grid-content bg-purple">
              <el-button type="primary">查询</el-button>
            </div>
          </el-col>
          <el-col :span="4">
            <div class="grid-content bg-purple-light">
              <el-button type="primary">添加用户</el-button>
            </div>
          </el-col>
        </el-row>
        <div class="content">
          <el-table :model="sbList" style="width: 100%">
            <el-table-column width="1080">
                <i class="el-icon-s-platform"></i>
                <span style="margin-left: 10px">设备名称{{ sbList.devName }}</span>
            </el-table-column>
            <el-table-column>
                <i class="el-icon-edit" @click="handleEdit()" ></i>
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
    </el-card>
  </d2-container>
</template>

<script>
// import { log } from 'util'
export default {
  name: 'sblist',
  data () {
    return {
      sbList: [],
      searchForm: {
        page: 1,
        per_page: 10
      },
      tot: 0,
      value1: '',
      currentPage: 5
    }
  },
  created () {
    this.getSbList()
  },
  methods: {
    // 获取设备列表
    getSbList () {
      let pro = this.$http.get('/dev')
      pro
        .then(result => {
          console.log(result)
        })
        .catch(err => {
          return this.$message.error('获得文章列表错误:' + err)
        })
    },
    handleSizeChange () {},
    handleCurrentChange () {},
    handleEdit () {},
    handleDelete () {}
  }
}
</script>
<style lang="scss" scoped>
  .el-icon-edit {
    margin-right: 20px;
  }

.grid-content {
  text-align: center;
  .el-button {
    width: 160px;
  }
}
.el-pagination {
  text-align: center;
}
</style>
