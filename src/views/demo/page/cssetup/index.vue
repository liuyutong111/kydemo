<template>
  <d2-container>
    <template slot="header">{{$t('page1')}}</template>
    <div class="parameter_setting parameter_head">
      <div class="parameter_trigger">
      <el-row :gutter="20">
  <el-col :span="4"><div class="grid-content bg-purple parameter_title">
    触发报警状态</div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
        <el-select v-model="value" placeholder="预警">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
      <el-select v-model="value" placeholder="确定数值（数字）预警">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
      <el-select v-model="value" placeholder="报警">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
    <el-col :span="5"><div class="grid-content bg-purple">
      <el-select v-model="value" placeholder="报警（数值）">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
</el-row>
     <el-row :gutter="20">
  <el-col :span="4"><div class="grid-content bg-purple"></div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
        <el-select v-model="value" placeholder="严重报警">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
      <el-select v-model="value" placeholder="严重报警（数值）">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
  <el-col :span="5"><div class="grid-content bg-purple">
      <el-select v-model="value" placeholder="请选择">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
    <el-col :span="5"><div class="grid-content bg-purple">
      <el-select v-model="value" placeholder="请选择">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
</el-row>
</div>
<!-- 采集时间 -->
<div class="parameter_time">
  <el-row :gutter="20">
  <el-col :span="6"><div class="grid-content bg-purple parameter_title">
    采集时间:</div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple">
        <el-select v-model="value" placeholder="15分钟">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple">
      <el-select v-model="value" placeholder="太">
    <el-option
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
    </div></el-col>
  <el-col :span="6"><div class="grid-content bg-purple">
    </div></el-col>
</el-row>
   </div>
   <!-- 单选按钮 -->
   <div class="parameter_button">
      <el-row :gutter="20">
  <el-col :span="6"><div class="grid-content bg-purple parameter_title">
    是否开启警报:</div></el-col>
  <el-col :span="18"><div class="grid-content bg-purple">
     <el-radio-group v-model="radio" @change="changeHandler">
     <el-radio :label="1">启用</el-radio>
     <el-radio :label="2">禁用</el-radio>
    </el-radio-group>
    </div></el-col>
</el-row>
   </div>
    </div>
    <div class="parameter_footer">
     <el-button type="primary" >立即创建</el-button>
     <el-button autofocus>取消</el-button>
    </div>
  </d2-container>
</template>

<script>
export default {
  name: 'cssetup',
  data() {
      return {
          radio: 1,
        options: [{
          value: '选项1',
          label: '黄金糕'
        }, {
          value: '选项2',
          label: '双皮奶'
        }, {
          value: '选项3',
          label: '蚵仔煎'
        }, {
          value: '选项4',
          label: '龙须面'
        }, {
          value: '选项5',
          label: '北京烤鸭'
        }],
        value: ''
      }
    },
    methods: {
    changeHandler(value) {
      console.log('改变之后的值是:' + value)
    }
  }
 
}
</script>
<style lang="scss">
.parameter_head{
  
  padding:50px 0;
}
.parameter_trigger{
   padding:40px 0;
 background-color: #fff;
 margin-bottom: 30px;
}
.parameter_time{
   padding:40px 0;
 background-color: #fff;
 margin-bottom: 30px;
}
.parameter_button{
   padding:40px 0;
 background-color: #fff;
 margin-bottom: 30px;
}
.parameter_title{
  margin-left: 100px;
}
.parameter_footer{
  text-align: center;
}
</style>