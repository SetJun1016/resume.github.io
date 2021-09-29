<template>
  <div class="info">
    <h1>项目经验/Profile</h1>
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
          name: '小海绵平台',
          skills: ' vue cube-ui 云闪付小程序 微信公众号 vuex webpack',
          content: '该项目主要是一个基于vue框架和cube-ui组件库开发的一个云闪付小程序和一个微信公众号，主要实现的功能有市场主流App推广，各银行独立活动，客户权益，商城购物，以及钱包提现，推广数据，线上审批等'
        },
        {
          name: '运营办公系统',
          skills: 'vue vuex echart element-ui webpack git ci/cd',
          content: '该项目是一个基于VUE框架和element-ui 组件库开发的一个公司运营的办公管理系统，主要实现的功能有用户登陆（限制权限）/公司部门管理/员工/员工管辖区域政策审批（抄送/评论等）/拜访信息填写/各政策数据实时统计/电子邮件/通讯录/日程表/等。'
        },
        {
          name: '负责人端系统',
          skills: 'vue vuex echart ant-design-vue webpack git ci/cd',
          content: '该项目是一个基于VUE框架和ant-design-vue组件库开发的一个负责人管理系统，主要实现功能有负责人管理自己的下属及员工，查看业务数据情况，审核审批，批量生成各产品推广码，动态创建表单，钱包提现功能等'
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
