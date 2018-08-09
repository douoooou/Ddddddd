<template>
  <div class="container">
    <el-breadcrumb separator-class="el-icon-arrow-right" class="breadcrumb">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item>文学</el-breadcrumb-item>
      <el-breadcrumb-item>文学</el-breadcrumb-item>
      <el-breadcrumb-item>全部</el-breadcrumb-item>
    </el-breadcrumb>
    <table border="1px solid #000000" cellpadding="0" cellspacing="0" >
      <tr>
        <th class="height-60">作业标题</th>
        <td colspan="5" class="text-left">为什么信息技术的更新对教育产生了影响？</td>
      </tr>
      <tr>
        <th class="height-40">所属章节</th>
        <td class="text-left len-mid">第一周 第二单元 网络信息的影响</td>
        <th>讲师</th>
        <td>张雪梅</td>
        <th>截止时间</th>
        <td>2018.09.27 14:00</td>
      </tr>
      <tr>
        <th class="height-40">作业内容</th>
        <td colspan="5" class="text-left">为什么信息技术的更新对教育产生了影响？</td>
      </tr>
      <tr>
        <th class="height-60">作业附件</th>
        <td colspan="5" class="text-left">网络信息技术的影响资料.doc
          <ul class="pull-right">
            <li class="list-inline"><button class="btn-mid btn-primary el-button">预览</button></li>
            <li class="list-inline"><button class="btn-mid btn-primary el-button">下载</button></li>
          </ul>
        </td>
      </tr>
<tr>
  <th class="height-60">提交作业</th>
    <td colspan="5">
      <span class="pull-right pad-right-30 mar-top">
        提交人数：20/200
     </span>
     <div class="pull-left">
        <ul>
          <li>
            <span class="pad-right-30">王东东网络信息技术作业2-1.doc</span>
            <button class="btn-mid btn-primary el-button">上传</button>
            <button class="btn-mid btn-primary el-button">提交</button>
          </li>
          <li>
            <span class="pad-right-30">王东东网络信息技术作业2-1.doc</span>
            <button class="btn-mid btn-primary el-button">上传</button>
            <button class="btn-mid btn-primary el-button">提交</button>
          </li>
        </ul>
        <li class="pull-left mar-botm"><button class="btn-mid el-button btn-primary">添加</button></li>
     </div>
    </td>

</tr>
<tr>
  <th class="height-60">作业状态</th>
  <td colspan="5">
    <span class="pull-left mar-left">批阅中</span>
    <span class="pull-right pad-right-30">
      <a>查看成绩</a>
      <a @click="others = true">查看其他成员作业</a>
    </span>
  </td>
</tr>

</table>
<!--<el-dialog title="其他学员作业" :visible.sync="others">
  <hr>
  <ul class="list-inline">
    <li class="list-inline">王豆豆</li>
    <li class="list-inline">100分</li>
    <li class="list-inline">课程学习...doc</li>
  </ul>
</el-dialog> -->
<el-dialog title="其他学员作业" :visible.sync="others">
  <el-table :data="othersWorkData">
    <el-table-column property="name" label="姓名" width="150"></el-table-column>
    <el-table-column property="score" label="分数" width="200"></el-table-column>
    <el-table-column property="title" label="作业题目"></el-table-column>
  </el-table>
</el-dialog>
</div>


</template>

<script>
export default {
  name: 'workDetail',
  data () {
    return {
      othersWorkData: [{
        name: '王豆豆',
        score: '100分',
        title: '课程学习...doc'
      }, {
        name: '王豆豆',
        score: '100分',
        title: '课程学习...doc'
      }, {
        name: '王豆豆',
        score: '100分',
        title: '课程学习...doc'
      }],
      others: false
    };
  },
  methods: {
    merge ({row, column, rowIndex, columnIndex}){
      console.log("111111");
      console.log(row);
      console.log("111111");
      console.log(column);
      console.log(rowIndex);
      console.log(columnIndex);
      return 1;
    }
  }
};
</script>

<style scoped lang="less">
  .container table {
    text-align: center;
    margin-top: 50px;
  }
  table {
    width: 100%;
    border: 1px solid rgb(221, 221, 221)
  }
  th {
    text-align: center;
    width: 10%;
  }
  .text-left {
    text-align: left;
    padding-left: 30px;
  }
  .text-right {
    text-align: right;
  }
  .text-center {
    text-align: center;
  }
  .height-40{
    height: 40px;
  }
  .height-60{
    height: 60px;
  }
  .len-mid {
    width: 48%;
  }
  .pull-right {
    float: right;
  }
  .pull-left {
    float: left;
  }
  .list-inline {
    display: inline;
  }
  .btn-mid {
    width: 90px;
    height: 35px;
    margin-right: 30px;
  }
  li {
    padding-left: 30px;
    list-style-type: none;
    padding-top: 20px;
  }
  .pad-right-30 {
    padding-right: 30px;
  }
  ul {
    list-style-type: none;
  }
  .mar-botm {
    margin-bottom: 30px;
  }
  .mar-top {
    margin-top: 20px;
  }
  .mar-left {
    margin-left: 30px;
  }
  a {
    cursor: pointer;
    text-decoration-line: none;
    margin-left: 20px;
  }
  .btn-primary {
    border-radius: 5px;
  }
</style>
