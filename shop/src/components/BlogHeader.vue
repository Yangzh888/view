<template>
    <div>
      <el-container >
    <el-header >
      <h2 class="headlogo">我的公司logo</h2>
      <el-col :span="3" class="userinfo">
        <el-dropdown>
          <i class="el-icon-setting" style="margin-right: 15px"></i>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>查看</el-dropdown-item>
            <el-dropdown-item>新增</el-dropdown-item>
            <el-dropdown-item>删除</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
        <span>王小虎</span>
      </el-col>
    </el-header>
    </el-container>
    </div>
</template>

<script>
export default {
  name: 'BlogHeader'
}
</script>
