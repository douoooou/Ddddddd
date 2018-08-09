<template>
  <div class="container">
    <el-breadcrumb separator-class="el-icon-arrow-right" class="breadcrumb">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item>文学</el-breadcrumb-item>
      <el-breadcrumb-item>文学</el-breadcrumb-item>
      <el-breadcrumb-item>全部</el-breadcrumb-item>
    </el-breadcrumb>
    <div class="course-head">
      <div class="wraper">
        <h3 class="course-name">网课信息技术</h3>
        <el-row :gutter="20">
         <el-col :span="9">
           <img src="../index/hamburger.png" class="image">
         </el-col>
         <el-col :span="15">
           <div class="time">开课时间：2018年6月12日至2018年9月10日</div>
           <div class="teacher-name">授课讲师：王秀敏、郑荣奇</div>
           <p class="course-title">课程简介</p>
           <div class="course-info">急救知识、能力，围绕现代社会目前所能遇见的各类急救事件围绕现代社会目前所能遇见的各类急救事件围绕现代社会目前所能遇见的各类急救事件、急救环境而开展的一项普及急救知识的课急救知识、能力，围绕现代社会目前所能遇见的各类急救事件、急救环境而开展的一项普及急救知识的课急救知识、能力，围绕现代社会目前所能遇见的各类急救事件、急救环境而开展的一项普及急救知识的课</div>
           <div class="learning" v-if="logined">
             <el-button type="primary"><router-link to="/courseLearning">继续学习</router-link></el-button>
             <el-button>取消学习</el-button>
             <p class="progress">学习进度：课程学习 30% 作业完成60%  参与讨论 20%</p>
           </div>
           <el-button type="primary" v-else class="big-btn">加入学习</el-button>
         </el-col>
        </el-row>
      </div>
    </div>
    <div class="course-body">
      <el-row :gutter="20">
       <el-col :span="19">
         <div class="wraper tab-con">
           <el-tabs v-model="activeName" >
             <el-tab-pane label="课程大纲" name="first">
               <div class="tab-wraper">
                 <div  class="catalogue">
                   <ul>
                     <li class="section-title">第一周 计算机信息技术</li>
                     <ul class="section-de">
                       <li>第一节课：网络信息技术产生的影响</li>
                       <li>第2节课：网络信息技术产生的影响</li>
                       <li>第3课：网络信息技术产生的影响</li>
                     </ul>
                   </ul>
                   <ul>
                     <li class="section-title">第一周 计算机信息技术</li>
                     <ul class="section-de">
                       <li>第一节课：网络信息技术产生的影响</li>
                       <li>第2节课：网络信息技术产生的影响</li>
                       <li>第3课：网络信息技术产生的影响</li>
                     </ul>
                   </ul>
                 </div>
                 <div class="show-more">
                   <el-button type="text"><i class="el-icon-caret-bottom"></i>显示全部</el-button>
                 </div>
               </div>
             </el-tab-pane>
             <el-tab-pane label="作业区" name="second">
               <div class="tab-wraper  work-area">
                 <div  class="catalogue">
                   <ul>
                     <li class="section-title">第一周 计算机信息技术</li>
                     <ul class="section-de">
                       <li>
                         <el-row :gutter="15">
                           <el-col :span="20" class="de-left">
                             <el-row :gutter="15">
                               <el-col :span="12"><router-link to="/" class="ellipsis">第一节课：网络信息技术产生的影响网络信息技术产生的影响网络信息技术产生的影响网络信息技术产生的影响</router-link></el-col>
                               <el-col :span="9" class="time">截止时间：2018年9月27日 00:00</el-col>
                               <el-col :span="3" class="action">未提交</el-col>
                             </el-row>
                           </el-col>
                           <el-col :span="4">
                             <el-button type="primary" plain class="mid-btn">前往作业</el-button>
                           </el-col>
                         </el-row>
                       </li>
                     </ul>
                   </ul>
                 </div>
                 <div class="show-more">
                   <el-button type="text">
                     <el-pagination
                       layout="prev, next"
                       prev-text="上一页"
                      next-text="下一页">
                     </el-pagination>
                   </el-button>
                 </div>
               </div>
             </el-tab-pane>
             <el-tab-pane label="讨论区" name="third">
               <div class="tab-wraper  work-area">
                 <div  class="catalogue">
                   <ul>
                     <li class="section-title">第一周 计算机信息技术</li>
                     <ul class="section-de">
                       <li>
                         <el-row :gutter="15">
                           <el-col :span="20" class="de-left">
                             <el-row :gutter="15">
                               <el-col :span="12"><router-link to="/" class="ellipsis">第一节课：网络信息技术产生的影响网络信息技术产生的影响网络信息技术产生的影响网络信息技术产生的影响</router-link></el-col>
                               <el-col :span="9" class="time">截止时间：2018年9月27日 00:00</el-col>
                               <el-col :span="3" class="action">回复：24</el-col>
                             </el-row>
                           </el-col>
                           <el-col :span="4">
                             <el-button type="primary" plain class="mid-btn"><router-link to="/postdetail">前往帖子</router-link></el-button>
                           </el-col>
                         </el-row>
                       </li>
                     </ul>
                   </ul>
                 </div>
                 <div class="show-more">
                   <el-button type="text">
                     <el-pagination
                       layout="prev, next"
                       prev-text="上一页"
                       next-text="下一页">
                     </el-pagination>
                   </el-button>
                 </div>
               </div>
             </el-tab-pane>
             <el-tab-pane label="活动区" name="fourth">
               <div class="tab-wraper  work-area">
                 <div  class="catalogue">
                   <ul>
                     <li class="section-title">第一周 计算机信息技术</li>
                     <ul class="section-de">
                       <li>
                         <el-row :gutter="15">
                           <el-col :span="20" class="de-left">
                             <el-row :gutter="15">
                               <el-col :span="12"><router-link to="/" class="ellipsis">第一节课：网络信息技术产生的影响网络信息技术产生的影响网络信息技术产生的影响网络信息技术产生的影响</router-link></el-col>
                               <el-col :span="9" class="time">截止时间：2018年9月27日 00:00</el-col>
                               <el-col :span="3" class="action">投票</el-col>
                             </el-row>
                           </el-col>
                           <el-col :span="4">
                             <el-button type="primary" plain class="mid-btn">前往活动</el-button>
                           </el-col>
                         </el-row>
                       </li>
                     </ul>
                   </ul>
                 </div>
                 <div class="show-more">
                   <el-button type="text">
                     <el-pagination
                       layout="prev, next"
                       prev-text="上一页"
                       next-text="下一页">
                     </el-pagination>
                   </el-button>
                 </div>
               </div>
             </el-tab-pane>
           </el-tabs>
         </div>
         <!--/*推荐资料*/-->
         <p class="recommond-title">推荐资料</p>
         <div class="wraper recommond">
           <ul>
             <li class="item clearfix">
               <div class="pull-left">
                 <div class="icon"><img src="../common/header/logo.png"></div>
                 <p class="subject">网络信息技术与创新</p>
               </div>
               <div class="pull-right btn-group">
                 <el-button type="primary" class="mid-btn">预览</el-button>
                 <el-button type="info" class="mid-btn light-grey">下载</el-button>
               </div>
             </li>
           </ul>
         </div>
       </el-col>
       <el-col :span="5">
         <!--/*讲师简介*/-->
         <div class="wraper teacher">
           <h3 class="title">讲师简介</h3>
           <div class="info">简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介简介</div>
         </div>
         <!--/*评价*/-->
         <div class="wraper comment">
           <h3 class="title">
             <span >评价</span>
             <el-rate
             v-model="score"
             disabled
             text-color="#ff9900"
             score-template="{value}">
            </el-rate>
           </h3>
           <ul>
             <li class="ellipsis item">王**东一：老师讲的很清楚王**东一：老师讲的很清楚！...</li>
           </ul>
         </div>
       </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  name: "CourseListDetail",
  data () {
    return {
      activeName: 'first',
      score: 3.7,
      logined: true
    }
  }
}
</script>

<style scoped lang="less">
  .wraper{
    padding: 20px;
    background-color: #fff;
    margin-bottom: 20px;
  }
  .course-head{
    .course-name{
      text-align: center;
      font-weight: bold;
      padding-bottom: 15px;
      border-bottom:1px solid #eee;
      margin-bottom: 20px;
    }
    .image{
      width: 100%;
      max-height: 222px;
    }
    .time,.name,.course-info{
      line-height: 26px;
    }
    .course-info{
      height: 79px;
      margin-bottom: 20px;
      word-break:break-all;
      display:-webkit-box;
      -webkit-line-clamp:3;
      -webkit-box-orient:vertical;
      overflow:hidden;
    }
    .course-title{
      color: #999;
      margin-top: 20px;
    }
    .learning{
      .progress{
        display: inline-block;
        font-size: 12px;
        color: #999;
        margin-left: 20px;
      }
    }
  }
  .course-body{
    .tab-con{
      padding-bottom: 0;
      padding-top: 10px;
      .tab-wraper{
        height: 460px;
        position: relative;
        .catalogue{
          height: 408px;
          line-height: 34px;
          .section-de{
            color: #999;
            padding-left: 25px;
          }
        }
        &.work-area .section-de li{
          margin-bottom: 20px;
          &:hover{
            .de-left{
              background-color: #eee;
            }
          }
          .time{
            font-size: 12px;
          }
          .action{
            color: #333;
          }
        }
        &.work-area{
          .show-more{
            line-height: 0;
          }
        }
        .show-more{
          position: absolute;
          bottom: 0;
          left: 0;
          width: 100%;
          line-height: 58px;
          text-align: center;
          border-top: 1px solid #eee;
          button{
            color: #333;
            .el-icon-caret-bottom{
              margin-right: 10px;
            }
            &:hover{
              color: #29A3E9;
            }
          }
        }
      }
    }
    .recommond-title{
      font-size: 20px;
      margin-bottom: 8px;
    }
    .recommond{
      ul > li.item{
        border-bottom: 1px solid #eee;
        padding-bottom: 19px;
        height: 50px;
        .icon{
          width: 40px;
          height: 46px;
          display: inline-block;
          vertical-align: middle;
          margin-right: 30px;
          img{
            width: 100%;
          }
        }
        .subject{
          font-size: 16px;
          line-height: 46px;
          display: inline-block;
        }
        .btn-group{
          margin-top: 8px;
        }
        &:last-child{
          border-bottom: none;
          padding-bottom: 0;
        }
      }
    }
    .teacher{
      .title{
        padding-bottom: 8px;
      }
      .info{
        font-size: 12px;
      }
    }
    .comment{
      .title{
        padding-bottom: 7px;
        border-bottom: 1px solid #eee;
        .el-rate{
          display: inline-block;
          margin-left: 2%;
        }
      }
      .item{
        line-height: 38px;
        font-size: 12px;
      }
    }
  }
</style>
