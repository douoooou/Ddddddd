<template>
<div class="category-box">
  <el-row class="category">
    <el-col :span="3" v-for="item in sort" :key="item.id">{{item.title}}</el-col>
  </el-row>
  <el-row class="category2">
    <el-col :span="3" v-for="item in sort2" :key="item.id">{{item.title}}</el-col>
  </el-row>
</div>
</template>

<script>
export default {
  name: 'CourseCategory',
  data () {
    return {
      sort: [{
        title: '全部',
        id: '0'
      },
      {
        title: '语文',
        id: '1'
      },
      {
        title: '数学',
        id: '2'
      },
      {
        title: '英语',
        id: '3'
      },
      {
        title: '全部',
        id: '4'
      },
      {
        title: '语文',
        id: '5'
      },
      {
        title: '数学',
        id: '6'
      },
      {
        title: '教学资',
        id: '7'
      },
      {
        title: '全部',
        id: '8'
      },
      {
        title: '语文',
        id: '9'
      },
      {
        title: '数学',
        id: '10'
      },
      {
        title: '英语',
        id: '11'
      },
      {
        title: '全部',
        id: '12'
      },
      {
        title: '语文',
        id: '13'
      },
      {
        title: '数学',
        id: '14'
      },
      {
        title: '英语',
        id: '15'
      }],
      sort2: [{
        title: '全部',
        id: '0'
      },
      {
        title: '语文',
        id: '1'
      },
      {
        title: '数学',
        id: '2'
      },
      {
        title: '英语',
        id: '3'
      },
      {
        title: '全部',
        id: '4'
      },
      {
        title: '语文',
        id: '5'
      },
      {
        title: '数学',
        id: '6'
      },
      {
        title: '英语',
        id: '7'
      }
      ]
    };
  }
};
</script>

<style scoped lang="less">
.category-box {
  margin-bottom: 15px;
}
.category {
  border-bottom: 1px solid #eee;
  .el-col:hover{
    color: #29A3E9;
    cursor: pointer;
  }
}
.category2 {
  .el-col:hover{
    color: #29A3E9;
    cursor: pointer;
  }
}
.category2 .el-col,
.category .el-col {
  background: #fff;
  line-height: 61px;
  height: 61px;
  font-size: 14px;
  text-align: center;
}
</style>
