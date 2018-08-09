<template>
  <div class="container">
    <el-breadcrumb separator-class="el-icon-arrow-right" class="breadcrumb">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item>文学</el-breadcrumb-item>
      <el-breadcrumb-item>文学</el-breadcrumb-item>
      <el-breadcrumb-item>全部</el-breadcrumb-item>
    </el-breadcrumb>
    <CourseCategory></CourseCategory>
    <div class="navigation"><Navigation></Navigation></div>
    <div class="content">
      <el-tabs v-model="activeName" >
        <el-tab-pane label="全部（22）" name="first">
          <CourseList></CourseList>
        </el-tab-pane>
        <el-tab-pane label="正在进行" name="second">正在进行</el-tab-pane>
        <el-tab-pane label="未开始" name="third">未开始</el-tab-pane>
        <el-tab-pane label="已结束" name="fourth">已结束</el-tab-pane>
      </el-tabs>
      <div class="nav-toolbar-sort">
        <span>按开课时间<i class="el-icon-d-caret"></i></span>
      </div>
      <el-pagination class="page"
                     background
                     layout="prev, pager, next"
                     :total="1000">
      </el-pagination>
    </div>
  </div>
</template>

<script>
import CourseCategory from './CourseCategory';
import CourseList from './CourseList';
import Navigation from './Navigation';
export default {
  name: 'TheHome',
  data () {
    return {
      activeName: 'first'
    };
  },
  components: {
    CourseCategory,
    CourseList,
    Navigation,
  }
};
</script>

<style scoped lang="less">
  .content {
    background: #fff;
    padding: 4px 30px;
    position: relative;
    .nav-toolbar-sort{
      position: absolute;
      top: 4px;
      right: 30px;
      height: 40px;
      line-height: 40px;
      display: inline-block;
    }
  }
  .nav {
    border: none;
  }
  .el-header a {
    text-decoration: none;
    color: #666;
    line-height: 60px;
  }
</style>
