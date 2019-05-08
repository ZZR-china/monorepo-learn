<template>
  <div class="home-header">
    <el-row type="flex" class="row-bg" justify="center">
      <el-col :span="6" style="display:flex;justify-content: start;text-align:right;padding:15px 0;" :pull="0">
        <img src="../assets/images/pc_ico_logo2.png" style="width: auto;height: auto;" alt="logo">
      </el-col>
      <el-col :span="11" :push="0">
        <el-row :gutter="0" type="flex" justify="center" class="menu">
          <el-col :span="4" v-for="item in header" :key="item" class="menu-list">
            <span>{{item}}</span>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    msg: String
  },
  data () {
    return {
      header: [
        '快递查询',
        '产品体系',
        '快递合作',
        '商务合作',
        '城市合伙人',
        '关于我们',
      ],
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.home-header {
  height: 68px;
  box-shadow: 0px 2px 1px #f5f5f5;
  .el-row {
    .menu {
      font-size: 14px;
      &-list {
        padding: 20px 0;
      }
    }
  }
}
</style>
