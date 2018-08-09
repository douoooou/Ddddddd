<template>
  <div class="container">
    <el-breadcrumb separator-class="el-icon-arrow-right" class="breadcrumb">
      <el-breadcrumb-item to="{path: '/'}">首页</el-breadcrumb-item>
      <el-breadcrumb-item>全部课程计划</el-breadcrumb-item>
      <el-breadcrumb-item>计算机</el-breadcrumb-item>
      <el-breadcrumb-item>网络信息技术</el-breadcrumb-item>
      <el-breadcrumb-item>第一周</el-breadcrumb-item>
    </el-breadcrumb>

    <div class="discuss">
      <el-row>
        <el-col class="discuss-topic">
          <span>{{topic}}</span>
          <el-button type="text" @click="turnToLesson">来自{{lesson}}</el-button>
        </el-col>
        <el-col><p>{{question}}</p></el-col>
        <el-col class="discuss-info"><span>发表人：{{sponsor}}</span><span>发表时间：{{date}}</span></el-col>
      </el-row>
    </div>
    <div class="post">
      <el-row>
        <el-col :span="12" class="left">共{{totalNumber}}条评论</el-col>
        <el-col :span="12">
          <el-radio class="right2" v-model="radio" label="2">回复时间顺序</el-radio>
          <el-radio class="right1" v-model="radio" label="1">回复时间倒序</el-radio>
        </el-col>
      </el-row>
      <div class="commentList">
        <ul>
          <li v-for="item in commentList" :key="item.id">
            <div class="commentInfo"><span>{{item.userName}}
              <el-button class="role" type="primary" round v-if="item.userRole==='teacher' ">讲师</el-button></span>
              <span>{{item.date}}</span><span>{{item.time}}</span></div>
            <div class="content">{{item.commentContent}}</div>
          </li>
        </ul>
      </div>
      <div class="pagination">
        <el-pagination
          background
          v-if="paginationShow"
          layout="prev, pager, next"
          :current-page.sync="pageNo"
          :total="total"
          :pageSize="pageSize"
          @current-change="handleCurrentChange"></el-pagination>
      </div>
    </div>

    <div class="comment">
      <el-form ref="form" enctype="multipart/form-data">
        <el-form-item>
          <div class="el-upload-dragger">
            <el-upload
              drag
              action = "http://jsonplaceholder.typicode.com/posts/">
              <i class="el-icon-picture"></i>
            </el-upload>
          </div>
          <div>
            <label>
              <textarea class="edit_comment" v-model="commentContent" name="commentContent"></textarea>
            </label>
          </div>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitComment">发表回复</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: "PostDetail",
  data: function () {
    return {
      topic: '关于教学设计的讨论',
      lesson: '1.1第一讲/教学设计的基础',
      question: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean euismod bibendum laoreet. Proin gravida dolor sit amet lacus accumsan et viverra justo commodo. Proin sodales pulvinar tempor. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam fermentum, nulla luctus pharetra vulputate, felis tellus mollis orci, sed rhoncus sapien nunc eget.',
      sponsor: '张雪梅',
      date: '2018-04-27',
      totalNumber: '7',
      radio: '1',
      role: '讲师',
      total: 200, // item总数
      pageSize: 10, // 默认每页呈现10条item
      commentList: [
        {id: '1', userName: '张雪梅', userRole: 'teacher', date: '2017-08-09', time: '12:25', commentContent: 'Lorem ipsum dolor sit amet.'},
        {id: '2', userName: '张一一', userRole: 'student', date: '2017-08-09', time: '12:25', commentContent: 'Lorem ipsum dolor sit amet.'},
        {id: '3', userName: '李明', userRole: 'student', date: '2017-08-09', time: '12:25', commentContent: 'Lorem ipsum dolor sit amet.'},
        {id: '4', userName: '高三三', userRole: 'student', date: '2017-08-09', time: '12:25', commentContent: 'Lorem ipsum dolor sit amet.'},
        {id: '5', userName: '王小溪', userRole: 'student', date: '2017-08-09', time: '12:25', commentContent: 'Lorem ipsum dolor sit amet.'},
        {id: '6', userName: '张一一', userRole: 'student', date: '2017-08-09', time: '12:25', commentContent: 'Lorem ipsum dolor sit amet.'},
        {id: '7', userName: '张一一', userRole: 'student', date: '2017-08-09', time: '12:25', commentContent: 'Lorem ipsum dolor sit amet.'}
      ],
      pageNo: 1,
      totalPage: 0,
      paginationShow: true,
      commentContent: ''
    }
  },
  methods: {
    turnToLesson () {
      this.$router.replace('/coursedetail')
    },
    getPageData: function () {
      this.loading = true;
      this.$axios.get('url').then((res) => {
        console.log(res)
      });
    },
    // 点击下一页或者点击页码
    handleCurrentChange (val) {
      this.pageNo = val;
      this.getPageData();
    },
    submitComment () {
      var formData = new FormData(this.$refs.form); // 获取表单数据
      let config = {
        headers: {
          'Content-Type': 'multipart/form-data',
          'Authorization': '' // 添加头部信息
        }
      }
      axios.post('url', formData, config).then(res => {
        if (res.data.error_code === 0){
          this.tabshow = false;
          this.$emit('closeall', this.tabshow);
        }
      })
    }
  }
}
</script>

<style scoped lang="less">
  .discuss{
    border-bottom: 1px solid #979797;
    margin-bottom: 40px;
  }
  .discuss-topic{
    font-size: 18px;
  }
  .discuss-info{
    color: #999999;
    font-size: 14px;
    margin-top: 30px;
    margin-bottom: 10px;
  }
  .discuss-info span{
    margin-right: 20px;
  }
  .discuss-topic span{
    margin-right: 10px;
  }
  .left{
    float: left;
  }
  .right1{
    float: right;
    color: #999999;
    margin-right: 28px;
  }
  .right2{
    float: right;
    color: #999999;
  }
  .pagination{
    width: 400px;
    margin-right: auto;
    margin-left: auto;
  }
  .post{
    margin-bottom: 30px;
  }
  .commentList{
    margin-top: 30px;
  }
  .commentInfo{
    color: #999999;
    font-size: 12px;
    margin-bottom: 10px;
  }
  .commentInfo span{
    margin-right: 20px;
  }
  .content{
    margin-bottom: 50px;
    line-height: 22px;
    font-size: 14px;
  }
  .pagination .el-pager .number{
    font-style: normal;
    color: #5daf34;
  }
</style>
<style>
  .comment .el-upload-dragger .el-icon-picture{
    float: left;
    margin-left: 15px;
    margin-top: 4px;
    /*width: 30px;*/
  }
  .comment .el-upload-dragger{
    box-sizing: border-box;
    border: 1px solid #DDDDDD;
    border-radius: 3px;
    height: 27px;
    width: 1120px;
  }
  .comment .edit_comment{
    border-top: none;
    box-sizing: border-box;
    border-bottom: 1px solid #DDDDDD;
    border-right: 1px solid #DDDDDD;
    border-left: 1px solid #DDDDDD;
    /*border: none;*/
    height: 88px;
    width:1120px;
    border-radius: 3px;
  }
  .commentList .commentInfo .role{
    padding:  2px 6px;
    font-size: 10px;
    margin-left: 3px;
  }
</style>
