<template>
<div class="container">
  <!--面包屑导航-->
  <el-breadcrumb separator-class="el-icon-arrow-right" class="breadcrumb">
    <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
    <el-breadcrumb-item>文学</el-breadcrumb-item>
    <el-breadcrumb-item>文学</el-breadcrumb-item>
    <el-breadcrumb-item>全部</el-breadcrumb-item>
  </el-breadcrumb>
  <el-row :gutter="20">
   <el-col :span="5">
     <div class="wraper prev-learning">
       <h3 class="title"><img src="./images/pic-list.png"/>往期列表</h3>
       <ul>
         <li class="ellipsis section">第一周 计算机信息技术</li>
         <ul class="section-de">
           <li class="ellipsis item active"><router-link to="/">第一节课：网络信息网络信息...</router-link></li>
           <li class="ellipsis item"><router-link to="/">第一节课：网络信息网络信息...</router-link></li>
         </ul>
       </ul>
     </div>
   </el-col>
   <el-col :span="19">
     <div class="wraper learning">
       <h3 class="title">课程名称：网络发展</h3>
       <div class="learning-top-tab">
         <el-tabs type="card" v-model="activeName" @tab-click="handleClick">
           <el-tab-pane label="视频" name="video">
             <div class="tip clearfix"><span class="pull-left">授课教师：王秀英</span><span class="pull-right">课程评价</span></div>
             <TheVideo></TheVideo>
           </el-tab-pane>
           <el-tab-pane label="音频" name="audio">
             <div class="tip clearfix"><span class="pull-right">课程评价</span></div>
             <TheAudio></TheAudio>
           </el-tab-pane>
           <el-tab-pane label="文档" name="doc">
             <div class="tip clearfix"><span class="pull-right">课程评价</span></div>
             <TheDoc></TheDoc>
           </el-tab-pane>
           <el-tab-pane label="图片" name="image">
             <div class="tip clearfix"><span class="pull-right">课程评价</span></div>
             <TheImage></TheImage>
           </el-tab-pane>
         </el-tabs>
       </div>
     </div>
     <!--作业区等-->
     <div class="event-area wraper">
       <el-tabs v-model="evevtActiveName" >
         <el-tab-pane label="作业区" name="works">
           <div class="area">
             <p class="class-hour">第二周  第三课</p>
             <ul class="work">
               <li class="item">
                 <el-row :gutter="20" class="question">
                   <el-col :span="18" class="ellipsis">标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题</el-col>
                   <el-col :span="6" >提交截止时间：2018.09.27 14:00</el-col>
                 </el-row>
                 <el-row :gutter="20" class="state">
                   <el-col :span="18">
                     <div class="progress">
                       <span class="finshed">已提交</span>
                       <i></i>
                       <span class="finshed">已审阅</span>
                       <i></i>
                       <span>87</span>
                     </div>
                   </el-col>
                   <el-col :span="6"><el-button type="primary" class="mid-btn">前往作业</el-button></el-col>
                 </el-row>
               </li>
             </ul>
           </div>
         </el-tab-pane>
         <el-tab-pane label="讨论区" name="discuss"></el-tab-pane>
         <el-tab-pane label="活动区" name="activity"></el-tab-pane>
       </el-tabs>
     </div>
   </el-col>
  </el-row>
</div>
</template>

<script>

import TheVideo from './components/TheVido'
import TheDoc from './components/TheDoc'
import TheAudio from './components/TheAudio'
import TheImage from './components/TheImage'

export default {
  name: "CourseLearning",
  data () {
    return {
      activeName: 'video',
      evevtActiveName: 'works'
    };
  },
  components: {
    TheVideo,
    TheDoc,
    TheAudio,
    TheImage
  },
  methods: {
    handleClick (tab){
      console.log(tab.$el.innerHTML)
    }
  }
}
</script>

<style scoped lang="less">
  .wraper{
    padding: 10px 20px 20px 20px;
    background-color: #fff;
    margin-bottom: 20px;
  }
  .prev-learning{
    .title{
      font-size: 16px;
      text-align: center;
      border-bottom: 1px solid #eee;
      padding-bottom: 10px;
      line-height: 30px;
      vertical-align: middle;
      img{
        margin-right: 6px;
        display: inline-block;
      }
    }
    .section{
      font-size: 12px;
      margin-bottom: 15px;
      margin-top: 15px;
      line-height: 30px;
    }
    .section-de{
      font-size: 12px;
      line-height: 30px;
      .item{
        padding-left: 15px;
        margin-bottom: 10px;
        &.active, &:hover{
          a{
            color: #29A3E9;
            text-decoration: none;
          }
          background-color: rgba(41,163,233,0.15);
        }
      }
    }
  }
  .learning{
    .learning-top-tab{
      margin-top: 20px;
      .tip{
        line-height: 36px;
      }
    }
    .title{
      font-size: 18px;
      text-align: center;
      border-bottom: 1px solid #eee;
      padding-bottom: 10px;
      line-height: 30px;
    }
  }
  .event-area{
    .area{
      .class-hour{
        margin-top: 15px;
      }
      .work{
        margin-top: 10px;
        .item{
          border: 1px solid #eee;
          .question{
            padding: 0 15px;
            background-color: #eee;
            line-height: 40px;
            .el-col:last-child{
              font-size: 12px;
              text-align: right;
            }
          }
          .state{
            padding:20px 15px;
            .el-col:last-child{
              text-align: right;
            }
            .progress{
              span{
                line-height: 34px;
                &.finshed{
                  color: #29A3E9;
                }
              }
              i{
                display: inline-block;
                width: 60px;
                height: 1px;
                background-color: #ddd;
                line-height: 12px;
                margin-top: -6px;
                margin-left: 10px;
                margin-right: 10px;
                vertical-align: middle;
              }
            }
          }
        }
      }
    }
  }
</style>
