<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <el-input
      type="textarea"
      :autosize="{ minRows: 2, maxRows: 100}"
      placeholder="请输入内容"
      v-model="textarea"
    ></el-input>
    <el-button type="primary" @click="centerDialogVisible = true">修改</el-button>
    <el-dialog title="编辑<软件功能>内容" :visible.sync="centerDialogVisible" width="30%">
      <span>
        <el-input type="textarea" :autosize="{ minRows: 2, maxRows: 100}" v-model="textarea"></el-input>
      </span>
      <span slot="footer" class="dialog-footer">
        <el-button type="primary" @click="centerDialogVisible = false" >保存</el-button>
      </span>
    </el-dialog>
  </d2-container>
</template>

<script>
export default {
  name: 'xtsoftware',
  data () {
    return {
      textarea: '',
      centerDialogVisible: false
    }
  },
  methods: {

  }
}
</script>
<style lang="scss" scoped>
.el-button {
  margin-left: 95%;
  margin-top: 20px;
}
.el-dialog__wrapper {
    top:150px;
  }
.el-dialog {
  position: relative;
  .el-button {
    position: absolute;
    width: 120px;
    left: -55%;
    top: 80%;
  }
}
</style>
