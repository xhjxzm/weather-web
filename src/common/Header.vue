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
    <div class="menubtn">
      <i class="iconfont menu-icon">&#xe608;</i>
      更多
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonHeader',
  data () {
    return {
      province: '北京市',
      city: '北京市',
      temperature: 7
    }
  }
}
</script>

<style lang="stylus" scoped>
.header
  position: fixed
  z-index: 2
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
    border: 1px solid #ddd
    border-radius: 28px
    line-height: 36px
    font-size: 20px
    color: #ddd
    &:hover
      color: #fff
      border-color: #fff
    .menu-icon
      font-size: 20px

</style>
