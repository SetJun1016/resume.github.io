<template>
  <div class="info">
    <h1>技术栈/Skills</h1>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      leave-active-class="animated fadeOutRight"
      enter-active-class="animated fadeInLeft">
      <div class="cont"  v-if="show">
        <template v-for="skill in skills">
          <el-row :gutter="20" :key="skill.name">
            <el-col :span="8">
              <div class="left" :style="{backgroundColor: `${skill.background}`, height: `${(skill.child.length / 2) * 50 + ((skill.child.length / 2) - 1) * 20}px;`, lineHeight: `${(skill.child.length / 2) * 50 + ((skill.child.length / 2) - 1) * 20}px`}">
                <h2>{{skill.name}}</h2>
              </div>
            </el-col>
          <el-col :span="16">
              <el-row :gutter="10">
                <template v-for="child in skill.child">
                  <el-col :span="12"  :key="child.name">
                    <div class="right" :style="{backgroundColor: child.background}">
                      <h3>{{child.name}}</h3>
                    </div>
                  </el-col>
                </template>
              </el-row>
          </el-col>
        </el-row>
        </template>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  // let randomcolor = rgba()
  data () {
    return {
      show: false,
      skills: [
        {
          name: '基础',
          background: 'rgba(29, 218, 61, 0.2)',
          child: [
            {name: 'HTML5', background: 'rgba(29, 218, 61, 0.2)'},
            {name: 'CSS3', background: 'rgba(29, 218, 61, 0.2)'},
            {name: 'ES5 ES6 ES7', background: 'rgba(29, 218, 61, 0.2)'},
            {name: 'TypeScript', background: 'rgba(29, 218, 61, 0.2)'}
          ]
        },
        {
          name: '框架类',
          background: 'rgba(211, 184, 30, 0.2)',
          child: [
            {name: 'vue(熟练)', background: 'rgba(211, 184, 30, 0.2)'},
            {name: 'uni-app', background: 'rgba(211, 184, 30, 0.2)'},
            {name: 'react', background: 'rgba(211, 184, 30, 0.2)'},
            {name: '小程序开发', background: 'rgba(211, 184, 30, 0.2)'}
          ]
        },
        {
          name: '工具',
          background: 'rgba(232, 13, 24, 0.2)',
          child: [
            {name: 'Git', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'npm', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'webpack', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'vite', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'node', background: 'rgba(232, 13, 24, 0.2)'},
            {name: 'CI/CD', background: 'rgba(232, 13, 24, 0.2)'}
          ]
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
    .left {
      margin: 10px auto;
      width: 100%;
      // height: 120px;
      // background-color: rgba(211, 184, 30, 0.2);
      // line-height: 120px;
    }
    .right {
      height: 52px;
      // background-color: rgba(232, 13, 24, 0.2);
      line-height: 52px;
      margin: 0;
    }
  }
}
</style>
