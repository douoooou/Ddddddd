<template>
  <div class="container">
      <div class="navigation">
          <el-row>
              <el-col :span="6">                 
                 <div class="seach-wrapper">
                  <el-input  size="small">
                    <el-button slot="append" type="primary">搜索</el-button>
                  </el-input>
                </div>
              </el-col>
              <el-col :span="3" class="txt">
                开课时间 
              </el-col>
              <el-col :span="7">
                <div class="grid-content bg-purple-light">   
                    <el-col label="提交时间" class="submittime">
                        <el-col :span="11">
                          <el-date-picker type="date"  style="width: 100%"  size="small"></el-date-picker>
                        </el-col>
                        <el-col class="txt"  :span="2">至</el-col>
                        <el-col  :span="11">
                            <el-date-picker type="date" style="width: 100%"  size="small"></el-date-picker>
                        </el-col>
                      </el-col>
              </div>
            </el-col>

            <el-col :span="5" class="navigationbtn">
                <el-button type="primary"  size="small">创建课程</el-button>
                <el-button  size="small">教学数据</el-button>
              </el-col>            
        </el-row>
      </div>
  </div>

</template>

<script>
export default {
  name: "navigation"
};
</script>

<style scoped lang="less">
  .container{
    width:1120px;
    padding: 20px;
    background-color: #fff;
    margin-bottom: 20px;
  }
  .txt{
    margin-top: 5px;
    text-align: center;
  }
  .navigationbtn{
    margin-left: 130px;
  }

</style>
