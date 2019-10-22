<template>
  <div class="info">
    <h1>联系我/Contact</h1>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      enter-active-class="animated fadeInDown">
      <div class="cont"  v-if="show">
        <div class="assessment">
          <h2>自我评价</h2>
          <p>高效的自学能力,具备独立分析解决问题能力</p>
          <p>具有较强的自学能力，平时喜欢在CSDN博客上了解些 web前端的这个圈里面的一些新动态，了解一些新技术。</p>
          <p>短期规划，实现在现有技术的提升，同时实现在新技术上的突破。</p>
        </div>
        <div class="honor">
          <h2>兴趣爱好</h2>
          <p>爱看博客</p>
          <p>喜欢尝试新事物</p>
        </div>
        <div class="contact">
          <h2>联系我</h2>
          <p><i class="iconfont icon-shouji"></i>  18326174573</p>
          <p><i class="iconfont icon-youxiang"></i>  hjxyday11@163.com</p>
        </div>
        <div class="acount">
          <el-row>
            <template v-for="item in accounts">
              <el-col :span="6" :key="item.class">
                <div class="iconBox">
                  <a :href="item.link"><i class="iconfont iconSet" :class="item.class"></i></a>
                </div>
              </el-col>
            </template>
          </el-row>
        </div>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data () {
    return {
      show: false,
      accounts: [
        {class: 'icon-GitHub', link: '#'},
        {class: 'icon-sf', link: '#'},
        {class: 'icon-zhihu', link: '#'},
        {class: 'icon-xinlang', link: '#'}
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
a {
  text-decoration: none;
}
.info {
  .info;
  .cont {
    .cont;
    margin: 20px auto;
    background-color: rgba(233, 225, 225, .3);
    border-radius: 25px;
    padding: 30px 0;
    .acount {
      width: 30%;
      margin: 10px auto;
      .iconBox {
        width: 40px;
        height: 40px;
        border-radius: 20px;
        border: 1px solid rgba(9, 92, 49, .5);
        margin: 5px auto;
        background-color: rgba(13, 73, 87, 0.4);
        &:hover {
          background-color: rgba(13, 73, 87, 0.8);
        }
        .iconSet {
          font-size: 1.5rem;
          line-height: 40px;
          cursor: pointer;
          color: rgba(220, 228, 220, 0.7);
          &:hover {
            font-size: 1.8rem;
            color: rgba(220, 228, 220, 1);
          }
        }
      }
    }
  }
}
</style>
