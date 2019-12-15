<template>
  <d2-container>
    <el-container>
      <el-header><img src="./02/top.png" alt=""></el-header>
      <el-main>
        <el-row :gutter="30">
          <el-col :span="8"><div class="grid-content bg-purple"></div></el-col>
          <el-col :span="8"><div class="grid-content bg-purple"></div></el-col>
          <el-col :span="8"><div class="grid-content bg-purple"></div></el-col>
        </el-row>
        <div><img style="width:80%" src="./02/xingzhuang.png" alt=""><span style="display:inline-block">保存</span></div>
      </el-main>
    </el-container>
  </d2-container>
</template>
<style scoped>
  .el-header {
    background-color: transparent;
    text-align: center;
  }
  .el-main {
    background-color: transparent;
  }
  .el-main div span{
    width:18%;
    height:50px;
    background-image: url('./02/按钮.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
    margin-left: 2%;
    text-align: center;
    line-height: 50px;
    font-size: 22px;
    color:#fff
  }
  .el-main div span:hover{
    cursor: pointer;
  }
  .el-row {
    margin-bottom: 20px;
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: transparent;
  }
  .bg-purple {
    background: transparent;
    height: 630px;
  }
  .bg-purple-light {
    background: transparent;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
    background-image: url('./02/基本信息.png');
    background-size: 100% 100%;
    background-repeat: no-repeat
  }
  .row-bg {
    padding: 10px 0;
    background-color: transparent;
  }
</style>
<script>
export default {
  name: 'xtsetting',
  data () {
    return {

    }
  }
}
</script>
