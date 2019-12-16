<template>
  <div class="hello">
    <div>
      <div class="head clearfix">
        <div style="float:left">
          <a>预览</a><a>退一步</a><a>进一步</a><a>刷新</a>
        </div>
        <div style="float:right">
          <a>测试</a><a>保存</a><a>关闭</a>
        </div>
      </div>
      <div class="main">
        <div class="list">
          <ul>
            <li>
              <el-button @click="addComp()" ref="button">输入状态</el-button>
            </li>
          </ul>
        </div>
        <div class="uiBox">
          <el-form>
            <el-form-item
            v-for="item in form"
            :key="item.index"
            >
            <el-button>{{item.name}}</el-button>
            </el-form-item>
          </el-form>
        </div>
        <div class="editor">
          <el-tabs v-model="activeName" @tab-click="handleClick">
            <el-tab-pane label="全局" name="first">全局</el-tab-pane>
            <el-tab-pane label="属性" name="second">
              <el-form>
                <el-form-item label="组件信息">
                  <el-input v-model="EditForm.name"></el-input>
                </el-form-item>
              </el-form>
            </el-tab-pane>
            <el-tab-pane label="高级" name="third">高级</el-tab-pane>
          </el-tabs>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      activeName: 'second',
      form:[
        
      ],
      EditForm:{},
    }
  },
  methods: {
    handleClick(tab, event) {
        // console.log(tab, event);
    },
    addComp(){
      this.form.push({
        name:'开灯'
      })
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .clearfix::after{
    content:'';
    display: block;
    height: 0;
    clear: both;
  }
  .main{
    background: #e2e6ec;
    display: flex;
    justify-content: space-between;
  }
  .list{
    background: #f5f8fa;
    width: 20%;
    height: 90vh;
  }
  .uiBox{
    width: 26vw;
    height: 90vh;
    background: #111;
  }
  .editor{
    background: #f5f8fa;
    width: 20%;
    height: 90vh;
  }
</style>
