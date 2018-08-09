<template>
        <div class="container">
            <div class="coursebtn">
                <el-row>     
                  <el-col :span="24" class="navigationbtn">
                      <el-button  size="small">编辑</el-button>                      
                      <el-button  size="small">下架</el-button>
                      <el-button  size="small" @click="dialogFormVisible = true"  >创建作业</el-button>
                      <el-button  size="small" @click="dialogFormVisible2 = true" >发起讨论</el-button>                      
                      <el-button  size="small"  @click="dialogFormVisible3 = true">创建活动</el-button>                                                                
                    </el-col>            
                </el-row>
<!-- 创建作业dialog -->
              <el-dialog title="设计心理学技术网络信息技术课程简介" :visible.sync="dialogFormVisible" width="700px" center>
                  <el-form :model="form">
                      <!-- 作业标题 -->
                      <el-form-item label="作业标题"  >
                        <el-input v-model="form.name" auto-complete="off" placeholder="请输入活动名称" class="homework-input"></el-input>
                      </el-form-item>
                      <!-- 所属课程  -->
                      <el-form-item  label="所属课纲" >
                        <el-select v-model="form.activityweek"  placeholder="请选择" class="weekinput" >                         
                          <el-option label="第一周 教学设计" value="one"></el-option>
                          <el-option label="第二周 教学演示" value="two"></el-option>
                        </el-select>
                        <el-select v-model="form.activitychapter" placeholder="请选择" class="chapterinput">
                            <el-option label="1.1 第一章 教学设计基础理论" value="one"></el-option>
                            <el-option label="1.2 第二章 教学设计基础实践" value="two"></el-option>
                          </el-select>
                      </el-form-item>
                      <!-- 内容 -->
                      <el-form-item label="内容" :label-width="formLabelWidth" >
                          <el-input type="textarea" v-model="form.content" class="content" :rows="8"></el-input>
                      </el-form-item>
                      <!-- 上传文档 -->
                      <el-form-item  class="uploadocument">
                          <el-upload
                          class="upload-demo"
                          :on-preview="handlePreview"
                          :on-remove="handleRemove"
                          :before-remove="beforeRemove"
                           multiple
                          :limit="3"
                          :on-exceed="handleExceed"
                          :file-list="fileList">
                          <el-button size="small">上传文档</el-button>
                        </el-upload>
                      </el-form-item> 
                      <el-form-item>
                        <svg class="icon-svg" aria-hidden="true">
                          <use xlink:href="#el-icon-vue-doc"></use>
                        </svg>
                      </el-form-item>
                      <!-- 提交时间 -->
                      <el-form-item label="提交时间" class="submittime">
                          <el-col :span="7">
                            <el-date-picker type="date"  v-model="form.begindate" style="width: 100%" ></el-date-picker>
                          </el-col>
                          <el-col class="line" :span="2">至</el-col>
                          <el-col :span="7">
                              <el-date-picker type="date"  v-model="form.enddate" style="width: 100%"></el-date-picker>
                          </el-col>
                        </el-form-item>                                          
                  </el-form>  
                  <!-- 底部按钮 -->
                  <div slot="footer" class="dialog-footer">
                    <el-button type="primary" @click="dialogFormVisible = false" class="footerbtn">发布</el-button>          
                    <el-button @click="dialogFormVisible = false" class="footerbtn">取消</el-button>
                  </div>                                      
              </el-dialog>

<!-- 发起讨论dialog -->
           <el-dialog title="设计心理学技术网络信息技术课程简介" :visible.sync="dialogFormVisible2" width="700px" center>
                  <el-form :model="form">
                      <!-- 作业标题 -->
                      <el-form-item label="讨论主题"  >
                        <el-input v-model="form.name" auto-complete="off" placeholder="请输入活动名称" class="homework-input"></el-input>
                      </el-form-item>
                      <!-- 所属课程  -->
                      <el-form-item  label="所属课纲" >
                        <el-select v-model="form.activityweek"  placeholder="请选择" class="weekinput">
                          <el-option label="第一周 教学设计" value="one"></el-option>
                          <el-option label="第二周 教学演示" value="two"></el-option>
                        </el-select>
                        <el-select v-model="form.activitychapter" placeholder="请选择" class="chapterinput">
                            <el-option label="1.1 第一章 教学设计基础理论" value="one"></el-option>
                            <el-option label="1.2 第二章 教学设计基础实践" value="two"></el-option>
                          </el-select>
                      </el-form-item>
                      <!-- 内容 -->
                      <el-form-item label="内容" :label-width="formLabelWidth" >
                          <el-input type="textarea" v-model="form.content" class="content" :rows="8"></el-input>
                      </el-form-item>                                 
                  </el-form>  
                    <!-- 底部按钮 -->
                  <div slot="footer" class="dialog-footer">
                    <el-button type="primary" @click="dialogFormVisible2 = false" class="footerbtn">发表</el-button>          
                    <el-button @click="dialogFormVisible2 = false" class="footerbtn">取消</el-button>
                  </div>                                      
              </el-dialog>              
<!-- 创建活动dialog -->
              <el-dialog title="设计心理学技术网络信息技术课程简介" :visible.sync="dialogFormVisible3" width="700px" center>
                  <el-form :model="form">
                      <el-form-item  label="活动类型" >
                        <el-select v-model="form.activityweek"  placeholder="请选择" class="weekinput">
                          <el-option label="投票" value="one"></el-option>
                          <el-option label="投票" value="two"></el-option>
                        </el-select>
                      </el-form-item>                    
                      <!-- 作业标题 -->
                      <el-form-item label="活动标题"  >
                        <el-input v-model="form.name" auto-complete="off" placeholder="请输入活动名称" class="homework-input"></el-input>
                      </el-form-item>
                      <!-- 所属课程  -->
                      <el-form-item  label="所属课纲" >
                        <el-select v-model="form.activityweek"  placeholder="请选择" class="weekinput">
                          <el-option label="第一周 教学设计" value="one"></el-option>
                          <el-option label="第二周 教学演示" value="two"></el-option>
                        </el-select>
                        <el-select v-model="form.activitychapter" placeholder="请选择" class="chapterinput">
                            <el-option label="1.1 第一章 教学设计基础理论" value="one"></el-option>
                            <el-option label="1.2 第二章 教学设计基础实践" value="two"></el-option>
                          </el-select>
                      </el-form-item>   
                      <el-form-item class="box">
                          <el-form-item label="投票题型:" class="radiolabel">
                              <el-radio v-model="radio" label="1">单选</el-radio>
                              <el-radio v-model="radio" label="2">多选</el-radio>
                          </el-form-item> 
                          <el-form-item class="selbox">
                             <el-button class="selbtn">添加选项</el-button>
                             <p class="seltxt">投票选项不超过10个，选项限制50字内</p>                            
                          </el-form-item> 
                          <el-form-item class="selitem">
                            <el-radio v-model="radio"></el-radio>
                            <el-input auto-complete="off" placeholder="选项选项1111" class="selradio" size="small"></el-input>
                          </el-form-item>
                          <el-form-item  class="selitem">
                            <el-radio v-model="radio"></el-radio>
                            <el-input auto-complete="off" placeholder="选项选项2222" class="selradio" size="small"></el-input>
                          </el-form-item>
                          <el-form-item  class="selitem">
                            <el-radio v-model="radio"></el-radio>
                            <el-input auto-complete="off" placeholder="选项选项3333" class="selradio" size="small"></el-input>
                          </el-form-item>                          
                      <!-- 提交时间 -->
                      <el-form-item label="提交时间" class="submittime">
                          <el-col :span="7">
                            <el-date-picker type="date"  v-model="form.begindate" style="width: 100%" ></el-date-picker>
                          </el-col>
                          <el-col class="line" :span="2">至</el-col>
                          <el-col :span="7">
                              <el-date-picker type="date"  v-model="form.enddate" style="width: 100%"></el-date-picker>
                          </el-col>
                        </el-form-item>                           
                      </el-form-item>                                                   
                  </el-form>  
                    <!-- 底部按钮 -->
                  <div slot="footer" class="dialog-footer">
                    <el-button type="primary" @click="dialogFormVisible3 = false" class="footerbtn">发布</el-button>          
                    <el-button @click="dialogFormVisible3 = false" class="footerbtn">取消</el-button>
                  </div>                                      
              </el-dialog>              
            </div>          
        </div>
      
      </template>
      <script>
      export default {
        name: "navigation",
        data() {
          return {
                fileList: [{name: 'food.jpeg', url: 'https://fuss10.elemecdn.com/3/63/4e7f3a15429bfda99bce42a18cdd1jpeg.jpeg?imageMogr2/thumbnail/360x360/format/webp/quality/100'}, {name: 'food2.jpeg', url: 'https://fuss10.elemecdn.com/3/63/4e7f3a15429bfda99bce42a18cdd1jpeg.jpeg?imageMogr2/thumbnail/360x360/format/webp/quality/100'}],
                dialogFormVisible: false,
                dialogFormVisible2: false,
                dialogFormVisible3: false,
                form: {
                  name:'',
                  activityweek:'',
                  activitychapter:'',
                  content:'',
                  begindate: '',
                  enddate: '',
                  delivery: false,
                  type: [],
                  resource: '',
                  desc: ''
                },
                formLabelWidth: '65px',
                radio: '1'
          };
        },        
        methods: {
          handleRemove(file, fileList) {
            console.log(file, fileList);
          },
          handlePreview(file) {
            console.log(file);
          },
          handleExceed(files, fileList) {
            this.$message.warning(`当前限制选择 3 个文件，本次选择了 ${files.length} 个文件，共选择了 ${files.length + fileList.length} 个文件`);
          },
          beforeRemove(file, fileList) {
            return this.$confirm(`确定移除 ${ file.name }？`);
          }
        }        
      };
      </script>
      
      <style scoped lang="less">
        .container{
          margin-bottom: 20px;         
        }
       .coursebtn{
           margin-left: 300px;
           margin-top: 10px;
           .el-button{
               margin-left: 0;
               margin-right: 10px;
           }         
       }
      .homework-input{
        width: 320px;
      }        
      .uploadocument{
          margin-left: 20px;
      }
      .line{
        text-align: center;
      }
      .box{
          width: 600px;
          height: 334px;
          border: 1px solid #CCCCCC;
          padding-left: 20px;
      }
      .selbox{
        margin-top: 15px;
        margin-left: 20px;
        margin-bottom: 15px;
      }
      .selbtn{
        float: left;
      }
      .seltxt{
          font-family: PingFangSC-Regular;
          font-size: 12px;
          color: #999999;
          letter-spacing: 0;
          line-height: 12px;
          float: left;
          margin-top: 22px;
      }
      .uploadocument{
        margin-left: 60px;
        
      }
      .icon-svg{
        margin-left: 60px;
        font-size: 42px;
        line-height: 100px;
        color:#333;
        -webkit-transition: font-size 0.25s ease-out 0s;
        -moz-transition: font-size 0.25s ease-out 0s;
        transition: font-size 0.25s ease-out 0s;
      }
      .selradio{
        width: 220px;
      }
      .selitem{
        margin-top: 6px;
        margin-left: 40px;  
      }
      .submittime{
        margin-top: 20px;
      }
      </style>
      