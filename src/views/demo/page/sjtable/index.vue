<template>
  <d2-container>
    <template slot="header">
        <el-header><img src="./03/top.png" alt=""></el-header>
     <el-main>
      <el-card class="box-card">
       <div slot="header" class="clearfix">
        <el-row>
          <el-col :span="4">
            <div class="grid-content bg-purple">
              <el-dropdown>
                <el-button>
                  请选择设备名称
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
                  请选择设备线路
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
                  请选择所在区域
                  <i class="el-icon-arrow-down el-icon--right"></i>
                </el-button>
                <el-dropdown-menu slot="dropdown"></el-dropdown-menu>
              </el-dropdown>
            </div>
          </el-col>
          <el-col :span="5">
            <div class="grid-content bg-purple-light">
              <div class="block">
                <el-date-picker v-model="val" type="date" placeholder="选择日期"></el-date-picker>
              </div>
            </div>
          </el-col>
          <el-col :span="2">
            <div class="grid-content bg-purple">
              <el-button type="primary">查询数据</el-button>
            </div>
          </el-col>
          <el-col :span="2">
            <div class="grid-content bg-purple-light">
              <el-button type="primary" @click="centerDialogVisible = true">数据视图</el-button>
              <el-dialog title="数据视图" :visible.sync="centerDialogVisible" width="70%">
                <span>
                  <el-row :gutter="20">
                    <el-col :span="6">
                      <div class="grid-content bg-purple" :v-model="sbName">设备编码{{sbName}}</div>
                    </el-col>
                    <el-col :span="10">
                      <div class="block">
                        <el-date-picker
                          v-model="value"
                          type="datetimerange"
                          range-separator="-"
                          start-placeholder="开始日期"
                          end-placeholder="结束日期"
                        ></el-date-picker>
                      </div>
                    </el-col>
                    <el-col :span="4">
                      <div class="grid-content bg-purple">
                        <el-button type="primary">查询</el-button>
                      </div>
                    </el-col>
                    <el-col :span="4">
                      <div class="grid-content bg-purple">
                        <el-button type="primary">打印报表</el-button>
                      </div>
                    </el-col>
                  </el-row>
                </span>
                <span>
                  <el-table :data="tableData" stripe style="width: 100%">
                    <el-table-column prop="date" label="日期" width="135"></el-table-column>
                    <el-table-column prop="xl" label="设备线路" width="135"></el-table-column>
                    <el-table-column prop="sqz" label="当前值"  width="135"></el-table-column>
                    <el-table-column prop="ShiDu" label="环境湿度"  width="135"></el-table-column>
                    <el-table-column prop="SunDian" label="太阳能电压"  width="135"></el-table-column>
                    <el-table-column prop="dl" label="电池电压"  width="135"></el-table-column>
                    <el-table-column prop="cjd" label="采集点"  width="135"></el-table-column>
                    <el-table-column prop="time" label="上传时间"  width="135"></el-table-column>
                  </el-table>
                </span>
                <span slot="footer" class="dialog-footer">
                  <el-button type="primary" @click="centerDialogVisible = false" class="btn">保存</el-button>
                </span>
              </el-dialog>
            </div>
          </el-col>
          <el-col :span="2">
            <div class="grid-content bg-purple-light">
              <el-button type="primary">下载报表</el-button>
            </div>
          </el-col>
        </el-row>
        <div class="content">
          <el-table :data="sjList" style="width: 100%">
            <el-table-column prop="SheBei" label="设备"></el-table-column>
            <el-table-column prop="xl" label="设备线路"></el-table-column>
            <el-table-column prop="dqz" label="当前值"></el-table-column>
            <el-table-column prop="cjd" label="采集点"></el-table-column>
            <el-table-column prop="SunDian" label="太阳能电压"></el-table-column>
            <el-table-column prop="dl" label="电池电压"></el-table-column>
            <el-table-column prop="ShiDu" label="环境湿度"></el-table-column>
            <el-table-column prop="option" label="安装位置"></el-table-column>
            <el-table-column prop="time" label="上传时间"></el-table-column>
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
      </el-main>
    </template>

  </d2-container>
</template>

<script>
export default {
  name: 'sjtable',
  data () {
    return {
      value: '',
      sbName: 'xxxxx',
      centerDialogVisible: false,
      searchForm: {
        page: 1,
        per_page: 10
      },
      tot: 0,
      val: '',
      currentPage: 5,
      sjList: [
        {
          SheBei: 'xxxx',
          xl: 'xxxx',
          dqz: 'xxxx',
          cjd: 'xxxx',
          SunDian: 'xxxx',
          dl: 'xxxx',
          ShiDu: 'xxxx',
          option: 'xxxx',
          time: 'xxxx'
        }
      ],
      tableData: [{
        date: '',
        xl: '',
        dqz: '',
        cjd: '',
        SunDian: '',
        dl: '',
        ShiDu: '',
        time: ''
      }]
    }
  },
  methods: {
    handleSizeChange () {},
    handleCurrentChange () {}
  }
}
</script>
<style lang="scss" scoped>
 .el-header {
    background-color: transparent;
    text-align: center;
  }
  .el-main {
    background-color: transparent;
  }
.el-pagination {
  margin-top: 20px;
}
.text {
  font-size: 14px;
}

.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both;
}

.box-card {
  width: 100%;
}
.el-pagination {
  text-align: center;
}
.el-dialog__wrapper {
  top: 150px;
}
.el-dialog {
  position: relative;
  .el-button {
    width: 120px;
  }
  .btn {
    position: absolute;
    width: 120px;
    left: 40%;
    top: 90%;
  }
}
</style>
