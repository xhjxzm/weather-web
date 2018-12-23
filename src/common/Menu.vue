<template>
  <div class="menu">
    <ul>
      <li>首页</li>
      <li>下载</li>
      <li>天气服务</li>
      <li>资讯</li>
      <li>关于我们</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'MenuDetail'
}
</script>

<style lang="stylus" scoped>
.menu
  position: fixed
  right: 0px
  top: 0
  bottom: 0
  width: 134px
  padding: 0 20px
  box-sizing: border-box
  background: rgba(0, 0, 0, .7)
  color: #fff
  ul
    margin-top: 100px
    li
      line-height: 40px
      border-bottom: 1px solid #000
</style>
