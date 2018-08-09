<template>
    <el-row class="main-list">
      <el-col :span="24" class="list-item">
        <el-col :span="7" class="img">
          <div class="statewill"><p>正在进行</p></div>
            <router-link to="/coursedetail"><img src="../../assets/images/hamburger.png" alt="">
            </router-link>           
        </el-col>
        <el-col :span="17">
           <router-link to="/coursedetail"><p class="title">设计心理学技术网络信息技术课程简介2</p></router-link> 
          <p><span>讲师：</span><span>王陶阳2</span></p>
          <p><span>课程时间：</span><span>2018.09.27——'2018.09.29'</span></p>
          <p class="course-intro"><span>课程简介：</span><span>在规定时间内学习完所有课程，完成课后检测并按时提交，且在规定时间内参加考试并且合格者可获得证书课程简介：在规定时间内学习完所有课程，完成课后检测并按时提交，且在规定时间内参加考试并且合格者可获得证书2</span></p>
          <Coursebtn></Coursebtn>
        </el-col>
      </el-col>
    </el-row>
</template>

<script>
import Coursebtn from './Coursebtn.vue';
export default {
  name: "CourseList",
  data(){
    return{
      state:"即将开始",
      yel:true,
    }
  },
  components: {
    Coursebtn,
  }
}
</script>

<style scoped lang="less">
  .main-list .img img {
    width: 265px;
    height: 165px;
  }
  .main-list .list-item {
    padding: 30px 20px;
    border-bottom: 1px solid #eee;
  }
  .main-list .list-item:hover {
    background: #eee;
  }
  .main-list .el-col-17 .title {
    margin-bottom: 40px;
  }
  .main-list .el-col-17 p {
    margin: 5px 0;
  }
  .main-list .el-col-17 p span {
    font-size: 12px;
    color: #666;
    line-height: 20px;
  }
  .main-list .el-col-17 .course-intro span {
    color: #333;
  }


  .img{
      position:relative;
      .statewill{
        margin-left: -5px;
        margin-top: 25px;
        width:80px;
        height: 28px;
        position:absolute;
        background-color: #FFBB46;
        p{
        padding-top: 7px;
        text-align: center;
        // padding-left: 20px;
        font-family: PingFangSC-Regular;
        font-size: 12px;
        color: #FFFFFF;
        letter-spacing: 0;
        line-height: 12px; 
        }     
      }
      .doing{
        background-color: blue;
      }
      .done{
        background-color: gray;        
      }
    }
</style>
