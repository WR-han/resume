<template>
  <div id="app" ref="123">
    <el-menu
      default-active="1"
      class="left-menu"
      background-color="#1E1F1C"
      text-color="#BBBBBB"
      active-text-color="#ffffff"
      :collapse="isCollapse"
    >
      <el-menu-item
        style="top: 0"
        index="About Me"
        @click="handleSelect('about')"
      >
        <i class="el-icon-receiving"></i>
        <span slot="title">与我相关</span>
      </el-menu-item>

      <el-menu-item
        style="top: 56px"
        index="Work Experience"
        @click="handleSelect('work')"
      >
        <i class="el-icon-receiving"></i>
        <span slot="title">工作经验</span>
      </el-menu-item>

      <el-menu-item
        style="top: 112px"
        index="Skills"
        @click="handleSelect('skills')"
      >
        <i class="el-icon-receiving"></i>
        <span slot="title">专业技能</span>
      </el-menu-item>

      <!-- <el-menu-item style="top: 56px" index="2">
        <i class="el-icon-receiving"></i>
        <span slot="title">11111111111</span>
      </el-menu-item>

      <el-menu-item style="top: 56px" index="2">
        <i class="el-icon-receiving"></i>
        <span slot="title">11111111111</span>
      </el-menu-item>

      <el-menu-item style="top: 56px" index="2">
        <i class="el-icon-receiving"></i>
        <span slot="title">11111111111</span>
      </el-menu-item> -->
    </el-menu>

    <div class="right-block">
      <main>
        <el-row>
          <el-col class="main-left" :md="8">
            <el-card id="about" shadow="always">
              <div slot="header" class="clearfix">
                <i class="el-icon-user-solid"></i>
                <el-divider direction="vertical"></el-divider>
                <span>与我相关 </span>
                <span class="small-font"> About Me</span>
              </div>
              <div class="card-body">
                <div class="flex">
                  <el-avatar
                    src="http://canadasummer.cn/static/social_github.svg"
                  ></el-avatar>
                  <div>
                    <a href="https://github.com/WR-han" target="_blank"
                      >github.com/WR-han</a
                    >
                  </div>
                </div>
                <div class="flex">
                  <el-avatar
                    src="http://canadasummer.cn/static/social_wechat.svg"
                  ></el-avatar>
                  <div>17764032120</div>
                </div>
                <div class="flex">
                  <el-avatar
                    src="http://canadasummer.cn/static/dingtalk.svg"
                  ></el-avatar>
                  <div>wrhan27</div>
                </div>
              </div>
            </el-card>

            <el-card id="work" shadow="always">
              <div slot="header" class="clearfix">
                <i class="el-icon-s-cooperation"></i>
                <el-divider direction="vertical"></el-divider>
                <span>工作经历 </span>
                <span class="small-font"> Work Experience</span>
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
            <el-card id="skills" shadow="always">
              <div slot="header" class="clearfix">
                <i class="el-icon-s-cooperation"></i>
                <el-divider direction="vertical"></el-divider>
                <span>专业技能 </span>
                <span class="small-font"> Skills</span>
              </div>
              <div class="card-body">
                <el-collapse v-model="activeNames">
                  <el-collapse-item name="1">
                    <template slot="title">后端开发</template>

                    <el-timeline>
                      <el-timeline-item timestamp="Python" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">语言使用</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">多进程 / 多线程</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">异步编程</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>

                      <el-timeline-item timestamp="框架" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">Django</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">
                            Django REST framework
                          </div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">Flask</div>
                          <el-rate
                            v-model="two"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">FastAPI</div>
                          <el-rate
                            v-model="two"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>
                    </el-timeline>
                  </el-collapse-item>

                  <el-collapse-item name="2">
                    <template slot="title">前端开发</template>

                    <el-timeline>
                      <el-timeline-item timestamp="静态页面" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">HTML5</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>

                        <div class="skills-item">
                          <div class="skills-item-title">CSS3</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>

                        <div class="skills-item">
                          <div class="skills-item-title">响应式设计</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>

                      <el-timeline-item timestamp="JavaScript" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">语言使用</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">jQuery</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">Promise异步</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">
                            ajax / axios / fetch
                          </div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>

                      <el-timeline-item timestamp="框架" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">VUE</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">Bootstrap</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">Layui</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">uni-app</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>

                      <el-timeline-item timestamp="UI组件库" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">Element</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>

                        <div class="skills-item">
                          <div class="skills-item-title">Vant</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>
                    </el-timeline>
                  </el-collapse-item>

                  <el-collapse-item name="3">
                    <template slot="title">其他</template>

                    <el-timeline>
                      <el-timeline-item timestamp="数据库" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">MySQL</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">redis</div>
                          <el-rate
                            v-model="two"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>

                      <el-timeline-item timestamp="项目相关" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">Linux操作</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">Git</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">uWSGI</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">Nginx</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>

                      <el-timeline-item timestamp="云服务器" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">云服务器配置</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">
                            阿里云oss / 腾讯云cos ,相关SDK / API
                          </div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>

                      <el-timeline-item timestamp="其他的其他" placement="top">
                        <div class="skills-item">
                          <div class="skills-item-title">PhotoShop / 蓝湖</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">烹饪</div>
                          <el-rate
                            v-model="four"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                        <div class="skills-item">
                          <div class="skills-item-title">原型图 / 墨刀</div>
                          <el-rate
                            v-model="three"
                            :icon-classes="iconClasses"
                            disabled-void-icon-class="el-icon-circle-check"
                            :colors="['#FFD700', '#F7BA2A', '#FF9900']"
                            disabled
                          >
                          </el-rate>
                        </div>
                      </el-timeline-item>
                    </el-timeline>
                  </el-collapse-item>
                </el-collapse>
              </div>
            </el-card>
          </el-col>
        </el-row>
      </main>
    </div>
  </div>
</template>

<script>
import leftCard from "./components/leftCard";
export default {
  name: "App",
  components: {},
  props: {},
  data() {
    return {
      activeNames: ["1", "2", "3"],
      four: 4,
      three: 3,
      two: 2,
      iconClasses: ["el-icon-success", "el-icon-success", "el-icon-success"], // 等同于 { 2: 'icon-rate-face-1', 4: { value: 'icon-rate-face-2', excluded: true }, 5: 'icon-rate-face-3' }
    };
  },
  methods: {
    handleSelect(id) {
      document.getElementById(id).scrollIntoView({ behavior: "smooth" });
    },
  },
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

.small-font {
  font-size: 12px;
  font-weight: normal;
  line-height: 15px;
}

#app {
  transition: 0.5s;
  display: flex;
  background: #eeeeee;
}

main {
  max-width: 1140px;
  margin: 20px auto;
  background: white;
  padding: 10px;
}

.right-block {
  width: 100%;
}

.left-menu {
  /* position: fixed !important; */
  z-index: 9;
  top: 0;
  min-height: 100vh;
}

.el-menu {
  width: 300px;
}

.el-menu-item {
  overflow: hidden;
  position: sticky !important;
}

.el-menu--collapse {
  min-width: 64px;
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
  font-weight: 700;
}

.main-left .el-card__header .el-divider {
  background-color: white;
}

.main-right .el-card__header {
  background-color: #989898 !important;
  color: black;
  font-weight: 700;
}

.main-right .el-card__header .el-divider {
  background-color: black;
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

#about .flex div {
  line-height: 40px;
  padding-left: 10px;
}
#about .flex {
  margin: 15px 0;
}

#about .el-card__body {
  padding-top: 0;
  padding-bottom: 0;
}

.el-collapse-item__content {
  padding: 10px 50px;
  padding-bottom: 10px !important;
}

.el-collapse-item__header {
  font-weight: 700 !important;
  font-size: 20px !important;
}

#skills .el-timeline-item__timestamp {
  font-size: 18px !important;
  font-weight: initial !important;
}

#skills .el-timeline-item {
  font-weight: 300 !important;
}

.skills-item {
  padding-left: 20px;
  margin: 5px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

#skills .el-divider--horizontal {
  margin-left: 20px;
}

.el-tooltip__popper.is-dark {
  left: 0 !important;
}

@media screen and (max-width: 420px) {
  #skills .el-collapse-item__content {
    padding: 0 5px !important;
  }

  #skills .el-timeline-item__wrapper {
    padding-left: 20px !important;
  }

  .skills-item {
    padding-left: 10px !important;
  }

  .skills-item-title {
    width: 85px;
  }

  #skills .el-rate__icon {
    font-size: 13px;
    line-height: 20px;
  }
}
</style>