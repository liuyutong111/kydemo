<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <div class="contain">
      <div class="box">
        <input type="text" placeholder="系统简介" class="title" />
        <br />
        <el-button class="zt">系统设置</el-button>
      </div>
      <div class="box">
        <input type="text" placeholder="用户管理" class="title" />
        <br />
         <el-button class="zt">设置管理</el-button>
      </div>
      <div class="box">
        <input type="text" placeholder="参数设定" class="title" />
        <br />
         <el-button class="zt">实时数据</el-button>
      </div>
      <div class="box">
        <input type="text" placeholder="数据报表" class="title" />
        <br />
         <el-button class="zt">日志查询</el-button>
      </div>
      <div class="box">
        <input type="text" placeholder="数据分析" class="title" />
        <br />
         <el-button class="zt">用户操作</el-button>
      </div>
      <div class="box">
        <input type="text" placeholder="软件功能" class="title" />
        <br />
         <el-button class="zt">系统版权信息说明</el-button>
      </div>
      <el-button type="primary">保存</el-button>
    </div>
  </d2-container>
</template>

<script>
export default {
  name: 'xtfeatures'
}
</script>
<style lang="scss" scoped>
.contain {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  .box {
    width: 400px;
    height: 210px;
    margin-right: 30px;
    margin-bottom: 30px;
    border: 1px solid #ccc;
    .title {
      text-align: center;
      width: 120px;
      height: 30px;
      margin-bottom: 10px;
    }
    .zt {
      font-size: 12px;
      margin-left: 10px;
    }
  }
  .el-button {
    margin-left: 85%;
  }
}
</style>
