<template>
  <div class="header">
    <div class="logo-wrapper">
      <img src="../assets/images/logo.png">
    </div>
    <div
      class="location"
      @mouseenter="handlePanelShow">
      <i class="iconfont location-icon">&#xe61e;</i>
      {{ province }} {{ city }}
      <em></em>
      <span class="temperature">{{ temperature }}&#176;</span>
      <i class="iconfont weather-icon">&#xe7a4;</i>
    </div>
    <div
      class="menubtn"
      @mouseenter="handleMenuShow"
      @mouseleave="handleMenuHide">
      <i class="iconfont menu-icon">&#xe608;</i>
      更多
    </div>
    <fade-animation>
      <div
        class="menu"
        v-if="showMenu"
        @mouseenter="handleMouseEnter"
        @mouseleave="handleMouseLeave"
        ref="menuPanel">
        <ul>
          <router-link to="/"><li>首页</li></router-link>
          <router-link to="/"><li>下载</li></router-link>
          <router-link to="/"><li>天气服务</li></router-link>
          <router-link to="/"><li>资讯</li></router-link>
          <router-link to="/"><li>关于我们</li></router-link>
        </ul>
      </div>
    </fade-animation>
    <div
      class="weather-panel"
      ref="weatherPanel">
      <div class="panel-head">
        <span>北京</span>
        <span>12月29日 农历十一月廿三</span>
        <router-link to="/home">详情
          <i class="iconfont more-icon">&#xe66b;</i>
        </router-link>
      </div>
      <div class="panel-body">
        <ul>
          <li>昨天</li>
          <li>12/28</li>
          <li>-4&#176;</li>
          <li>晴</li>
          <li>晴</li>
          <li>西北风</li>
          <li>优</li>
        </ul>
        <ul>
          <li>昨天</li>
          <li>12/28</li>
          <li>-4&#176;</li>
          <li>晴</li>
          <li>晴</li>
          <li>西北风</li>
          <li>优</li>
        </ul>
        <ul>
          <li>昨天</li>
          <li>12/28</li>
          <li>-4&#176;</li>
          <li>晴</li>
          <li>晴</li>
          <li>西北风</li>
          <li>优</li>
        </ul>
        <ul>
          <li>昨天</li>
          <li>12/28</li>
          <li>-4&#176;</li>
          <li>晴</li>
          <li>晴</li>
          <li>西北风</li>
          <li>优</li>
        </ul>
        <ul>
          <li>昨天</li>
          <li>12/28</li>
          <li>-4&#176;</li>
          <li>晴</li>
          <li>晴</li>
          <li>西北风</li>
          <li>优</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import FadeAnimation from 'common/Fade'

export default {
  name: 'CommonHeader',
  components: {
    FadeAnimation
  },
  data () {
    return {
      province: '北京市',
      city: '北京市',
      temperature: 7,
      showMenu: false,
      timer: null
    }
  },
  methods: {
    handleMenuShow () {
      this.showMenu = true
    },
    handleMenuHide () {
      let self = this
      self.timer = setTimeout(() => {
        this.showMenu = false
      }, 150)
    },
    handleMouseEnter () {
      clearTimeout(this.timer)
    },
    handleMouseLeave () {
      this.showMenu = false
    },
    handlePanelShow () {
      const Panel = this.$refs.weatherPanel
      let panelTop = Panel.offsetTop
      const self = this
      console.log(panelTop)
      self.timer = setInterval(() => {
        if (panelTop > -10) {
          clearInterval(self.timer)
        } else {
          panelTop += 90
          Panel.style.top = panelTop + 'px'
          console.log(panelTop)
        }
      }, 50)
    }
  }
}
</script>

<style lang="stylus" scoped>
.header >>> .router-link-active
  color: #fff

.header
  position: fixed
  z-index: 99
  top: 0
  left: 0
  display: flex
  align-items: center
  width: 100%
  padding: 0 14px
  box-sizing: border-box
  height: 80px
  color: #fff
  background: linear-gradient(rgba(0, 0, 0, .6), rgba(0, 0, 0, 0))
  .logo-wrapper
    width: 150px
    flex: 1
  .location
    width: 240px
    height: 38px
    padding: 0 20px 0 10px
    margin-right: 30px
    box-sizing: border-box
    border-radius: 28px
    background: rgba(0, 0, 0, 0.3)
    line-height: 38px
    cursor: pointer
    .location-icon
      font-size: 20px
      margin-right: 10px
    em
      display: inline-block
      width: 1px
      height: 20px
      background: #ddd
      margin: 0 10px
      vertical-align: -3px
    .temperature
      font-size: 18px
      font-weight: bold
    .weather-icon
      font-size: 20px
  .menubtn
    width: 100px
    height: 36px
    text-align: center
    border: 1px solid #fff
    border-radius: 28px
    line-height: 36px
    font-size: 20px
    color: #fff
    cursor: pointer
    .menu-icon
      font-size: 20px
  .menu
    position: fixed
    z-index: -1
    right: 0
    top: 0
    bottom: 0
    width: 130px
    padding: 0 20px
    box-sizing: border-box
    background: rgba(0, 0, 0, .7)
    color: #fff
    ul
      margin-top: 100px
      color: #fff
      li
        line-height: 40px
        border-bottom: 1px solid #000
  .weather-panel
    position: absolute
    top: -370px
    right: 30px
    width: 500px
    background: rgba(0, 0, 0, .7)
    .panel-head
      display: flex
      justify-content: space-between
      background: rgba(0, 0, 0, .9)
      height: 50px
      line-height: 50px
      padding: 0 20px
      .more-icon
        font-size: 12px
      a
        color: #fff
    .panel-body
      display: flex
      padding: 20px 0
      ul
        width: 100px
        text-align: center
        line-height: 40px
        border-right: 1px solid #777
        &:last-child
          border-right: none
</style>
