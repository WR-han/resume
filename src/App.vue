<template>
  <div id="app">
    <nav>
      <el-menu
        default-active="1"
        class="left-menu"
        background-color="#1E1F1C"
        text-color="#BBBBBB"
        active-text-color="#ffffff"
        :collapse="isCollapse"
      >
        <el-menu-item index="1">
          <i class="el-icon-receiving"></i>
          <span slot="title">11111111111</span>
        </el-menu-item>

        <el-menu-item index="2">
          <i class="el-icon-receiving"></i>
          <span slot="title">11111111111</span>
        </el-menu-item>
      </el-menu>
    </nav>

    <main>
      <el-row>
        <el-col class="main-left" :md="8">
          <el-card class="about" shadow="always">
            <div slot="header" class="clearfix">
              <span>卡片名称</span>
            </div>
            <div class="card-body">
              <div class="flex">
                <el-avatar
                  src="http://canadasummer.cn/static/social_github.svg"
                ></el-avatar>
                <div>123456</div>
              </div>
              <div class="flex">
                <el-avatar
                  src="http://canadasummer.cn/static/social_wechat.svg"
                ></el-avatar>
                <div>123456</div>
              </div>
              <div class="flex">
                <el-avatar
                  src="http://canadasummer.cn/static/dingtalk.svg"
                ></el-avatar>
                <div>123456</div>
              </div>
            </div>
          </el-card>

          <el-card class="work" shadow="always">
            <div slot="header" class="clearfix">
              <i class="el-icon-s-cooperation"></i
              ><el-divider direction="vertical"></el-divider>
              <span>卡片名称</span>
            </div>
            <div class="card-body">
              <el-timeline>
                <el-timeline-item timestamp="2018/4/12" placement="top">
                  <el-card>
                    <h4>更新 Github 模板</h4>
                    <p>王小虎 提交于 2018/4/12 20:46</p>
                  </el-card>
                </el-timeline-item>
                <el-timeline-item timestamp="2018/4/3" placement="top">
                  <el-card>
                    <h4>更新 Github 模板</h4>
                    <p>王小虎 提交于 2018/4/3 20:46</p>
                  </el-card>
                </el-timeline-item>
                <el-timeline-item timestamp="2018/4/2" placement="top">
                  <el-card>
                    <h4>更新 Github 模板</h4>
                    <p>王小虎 提交于 2018/4/2 20:46</p>
                  </el-card>
                </el-timeline-item>
              </el-timeline>
            </div>
          </el-card>
        </el-col>
        <el-col class="main-right" :md="16">
          <el-card class="skills" shadow="always">
            <div slot="header" class="clearfix">
              <span>卡片名称</span>
            </div>
            <div class="card-body">
              <el-collapse v-model="activeNames">
                <el-collapse-item name="1">
                  <template slot="title"> Python </template>
                  <el-timeline>
                    <el-timeline-item timestamp="aaaaa" placement="top">
                      123123
                    </el-timeline-item>
                    <el-timeline-item timestamp="aaaaa" placement="top">
                      123123
                    </el-timeline-item>
                  </el-timeline>
                </el-collapse-item>

                <el-collapse-item title="反馈 Feedback" name="2">
                  <div>
                    控制反馈：通过界面样式和交互动效让用户可以清晰的感知自己的操作；
                  </div>
                  <div>
                    页面反馈：操作后，通过页面元素的变化清晰地展现当前状态。
                  </div>
                </el-collapse-item>

                <el-collapse-item title="效率 Efficiency" name="3">
                  <div>简化流程：设计简洁直观的操作流程；</div>
                  <div>
                    清晰明确：语言表达清晰且表意明确，让用户快速理解进而作出决策；
                  </div>
                  <div>
                    帮助用户识别：界面简单直白，让用户快速识别而非回忆，减少用户记忆负担。
                  </div>
                </el-collapse-item>

                <el-collapse-item title="可控 Controllability" name="4">
                  <div>
                    用户决策：根据场景可给予用户操作建议或安全提示，但不能代替用户进行决策；
                  </div>
                  <div>
                    结果可控：用户可以自由的进行操作，包括撤销、回退和终止当前操作等。
                  </div>
                </el-collapse-item>
              </el-collapse>
            </div>
          </el-card>
        </el-col>
      </el-row>
    </main>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  props: {},
  data() {
    return {
      activeNames: ["1", "2", "3", "4"],
    };
  },
  methods: {},
  watch: {},
  computed: {
    isCollapse() {
      if (document.body.clientWidth < 1064) {
        return true;
      } else {
        return false;
      }
    },
  },
  created() {},
  mounted() {},
};
</script>

<style>
.flex {
  display: flex;
}
#app {
  transition: 0.5s;
  display: flex;
  background: #eeeeee;
}

main {
  width: 1000px;
  margin: 20px auto;
  background: white;
}

.left-menu {
  height: 100vh;
  position: fixed !important;
  z-index: 9;
  top: 0;
  min-height: 100vh;
  width: calc((100vw - 1060px) / 2);
  min-width: 64px;
}
.el-menu-item {
  overflow: hidden;
}

#app .el-card {
  margin: 10px 0;
  border-radius: 0;
}

.main-left,
.main-right {
  padding: 0 10px;
}

.main-left .el-card__header {
  background-color: #282c2b !important;
  color: white;
}

.main-right .el-card__header {
  background-color: #989898 !important;
  color: white;
}

.el-timeline {
  padding-left: 0;
}

.el-timeline-item__node {
  background-color: #282c2b !important;
}

.el-avatar {
  background-color: #282c2b !important;
}

.about .flex div {
  line-height: 40px;
  padding-left: 10px;
}
.about .flex {
  margin: 15px 0;
}

.about .el-card__body {
  padding-top: 0;
  padding-bottom: 0;
}

.el-collapse-item__content {
  padding: 10px 50px;
  padding-bottom: 10px !important;
}

.el-collapse-item__header{
  font-weight: 700;
  font-size: 20px !important;
}
</style>