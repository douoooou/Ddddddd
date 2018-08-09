<template>
  <div>
    <ul class="audio-wraper">
      <li class="item">
        <el-row :gutter="10">
          <el-col :span="2">
              <img src="./../../../assets/images/pic-doc.png" class="icon"/>
          </el-col>
          <el-col :span="18">
            <div class="left">
              <p class="title">文件名称文件名称文件名称文件名称.mp3</p>
              <p class="teacher">授课教师：王秀英</p>
            </div>
          </el-col>
          <el-col :span="4">
            <div class="right">
              <el-button type="primary" plain class="mid-btn pull-right">在线查看</el-button>
            </div>
          </el-col>
        </el-row>
      </li>
    </ul>
    <el-pagination class="page"
                   background
                   layout="prev, pager, next"
                   :total="1000">
    </el-pagination>
  </div>
</template>

<script>
export default {
  name: "TheDoc"
}
</script>

<style scoped lang="less">
  .audio-wraper{
    .item{
      height:60px;
      padding: 10px 20px;
      border-bottom: 1px solid #eee;
      -webkit-transition: background-color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
      transition: background-color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
      .icon{
        margin-top: 10px;
      }
      .mid-btn{
        margin-top: 13px;
      }
      .el-button--primary.is-plain{
        -webkit-transition: background-color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1), color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
        transition: background-color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1), color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
      }
      &:hover{
        background-color: #f5f7fa;
        .el-button--primary.is-plain{
          background-color: #29A3E9;
          color: #fff;
        }
      }
      .left{
        .title{
          line-height: 40px;
        }
        .teacher{
          line-height: 20px;
          font-size: 12px;
          color: #999;
        }
      }
      &:last-child{
        border-bottom: none ;
      }
    }
  }
  .page{
    margin-bottom: 0;
  }
</style>
