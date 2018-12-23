<template>
  <div class="header">
    <div class="logo-wrapper">
      <img src="../assets/images/logo.png">
    </div>
    <div class="location">
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

</style>
