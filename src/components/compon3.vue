<template>
  <div class="info">
    <h1>作品集/Profile</h1>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      enter-active-class="animated fadeInRight">
      <div class="cont"  v-if="show">
        <el-row :gutter="20">
          <template v-for="item in profiles">
            <el-col :key="item.name" :offset="6" :span="12" :xs="24">
              <div class="item">
                <h2 v-text="item.name"></h2>
                <p v-text="'技术栈: ' + item.skills"></p>
                <p v-text="item.content"></p>
              </div>
            </el-col>
          </template>
        </el-row>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data () {
    return {
      show: false,
      profiles: [
        {
          name: '心理健康平台',
          skills: ' vue框架 layui组件库 axios css3 echarts',
          content: '该项目是一个针对于对心理健康的进行评估并可以进行在线预约医生的平台，主要实现 的功能有身份证登录，心里评估，在线预约，自主预约，心理学介绍，答题游戏等 '
        },
        {
          name: 'OA办公系统',
          skills: 'vue vue-cli vue-router vuex axios html5 css3 echart element-ui',
          content: '该项目是一个基于VUE框架和element-ui 组件库开发的一个公司的办公管理软件，主 要实现的功能有用户登陆（限制权限）/公司部门管理/员工考勤管理/员工假期申请/员工薪资管理 /电子邮件/通讯录/日程表/等。'
        }
      ]
    }
  },
  methods: {
    timeout () {
      setTimeout(() => {
        this.show = true
      }, 1000)
    }
  },
  mounted () {
    this.timeout()
  }
}
</script>

<style lang="less" scoped>
@import '../less/index.less';
.info {
  .info;
  .cont {
    .cont;
    width: 90%;
    .item {
      background-color: rgba(59, 123, 13, 0.2);
      padding: 10px;
      border-radius: 15px;
      margin: 10px auto;
      @media screen and (max-width: 768px) {
        padding: 5px;
        margin: 5px auto;
      }
      &:hover {
        border-radius: 25px;
        background-color: rgba(10, 135, 87, 0.3);
      }
      p {
        text-align: left;
        text-indent: 28px;
        font-size: 1.1rem;
        line-height: 1.2;
        @media screen and (max-width: 768px) {
          text-indent: 12px;
          font-size: 0.7rem;
          line-height: 1.1;
        }
      }
    }
  }
}
</style>
