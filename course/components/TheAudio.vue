<template>
  <div>
    <ul class="audio-wraper">
      <li class="item">
        <el-row :gutter="10">
          <el-col :span="18">
            <div class="left">
              <p class="title">文件名称文件名称文件名称文件名称.mp3</p>
              <p class="teacher">授课教师：王秀英</p>
            </div>
          </el-col>
          <el-col :span="6">
            <div class="right">
              <audio src="https://ss1.baidu.com/8aQDcnSm2Q5IlBGlnYG/stat/ogg/xinsui.mp3" controls="controls"></audio>
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
  name: "TheAudio"
}
</script>

<style scoped lang="less">
.audio-wraper{
  .item{
    height: 60px;
    padding: 10px 20px;
    border-bottom: 1px solid #eee;
    -webkit-transition: background-color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
    transition: background-color 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
    &:hover{
      background-color: #f5f7fa;
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
