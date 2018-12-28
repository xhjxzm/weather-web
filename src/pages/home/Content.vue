<template>
  <div>
    <div class="section banner">
      <div class="text">
        天气改变命运
      </div>
    </div>
    <div class="section introdution">
      <div class="intro">
        <hgroup>
          <h2>短时预报</h2>
          <h3>Nowcasting</h3>
          <h3>一款实用雷达图像显示的短时临近预报</h3>
        </hgroup>
        <ul>
          <li>
            <h4>分钟级</h4>
            <span>短时预报精准到1分钟</span>
          </li>
          <li>
            <h4>公里级</h4>
            <span>预报范围缩小到1公里</span>
          </li>
          <li>
            <h4>AI智能</h4>
            <span>机器学习技术结合</span>
            <span>传统数值模式系统</span>
          </li>
          <li>
            <h4>可视化</h4>
            <span>全球预报数据可视化</span>
            <span>高分辨率模式预报系统</span>
          </li>
        </ul>
      </div>
    </div>
    <div class="section information">
      <div class="info">
        <hgroup>
          <h2>天气资讯</h2>
          <h3>Weather Information</h3>
          <router-link to="/home">更多资讯 ></router-link>
        </hgroup>
        <router-link
          tag="dl"
          to="/home">
          <dt>
            <img src="../../assets/images/info1.jpg">
          </dt>
          <dd>
            <h3>【以梦为马 明日天涯】奔赴一场贪心的美西环游（18天8000公里，总有一款国家公园适合你）</h3>
            <time>2018-12-28</time>
            <p>向往山川大海，不爱水泥森林，心驰良田桑竹之属，厌倦朝九晚五之桎梏。这年十一，我们在落基山邂逅.........</p>
          </dd>
        </router-link>
        <router-link
          tag="dl"
          to="/home">
          <dt>
            <img src="../../assets/images/info2.jpg">
          </dt>
          <dd>
            <h3>海米蒸娃娃菜</h3>
            <time>2018-12-28</time>
            <p>娃娃菜清甜，海米鲜美，淡淡的海味加上清爽口感的娃娃菜，既美味.........</p>
          </dd>
        </router-link>
        <router-link
          tag="dl"
          to="/home">
          <dt>
            <img src="../../assets/images/info3.jpg">
          </dt>
          <dd>
            <h3>烤箱版红烧鱼盖饭</h3>
            <time>2018-12-28</time>
            <p>香甜的酱汁，搭配新鲜的三文鱼，放入烤箱............</p>
          </dd>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeContent'
}
</script>

<style lang="stylus" scoped>
@import '~css/mixins.styl'
.section
  width: 100%
  height: 0
  padding-bottom: 50%
.banner
  background: url(../../assets/images/home1.jpg) no-repeat top center
  background-size: cover
  background-attachment: fixed
  position: relative
  .text
    position: absolute
    top: 50%
    left: 50%
    margin-top: -30px
    margin-left: -180px
    color: #fff
    font-size: 60px
.introdution
  background: url(../../assets/images/home2.jpg) no-repeat top center
  background-size: cover
  background-attachment: fixed
  padding: 60px 0 50% 0
  color: #fff
  .intro
    width: 600px
    margin: 0 auto
    overflow: hidden
    hgroup
      text-align: center
      margin-bottom: 40px
      h2
        font-size: 42px
      h3
        letter-spacing: 2px
        margin: 10px 0
    ul
      overflow: hidden
      width: 140px
      margin: 0 auto
      text-align: center
      li
        line-height: 24px
        margin-bottom: 20px
        h4
          font-weight: bold
        span
          display: block
.information
  background: url(../../assets/images/home3.jpg) no-repeat top center
  background-size: cover
  background-attachment: fixed
  color: #fff
  padding: 60px 0 50% 0
  .info
    width: 900px
    margin: 0 auto
    overflow: hidden
    hgroup
      text-align: center
      margin-bottom: 40px
      h2
        font-size: 42px
      h3
        letter-spacing: 2px
        margin: 10px 0
      a
        color: #fff
    dl
      width: 230px
      float: left
      margin-right: 105px
      cursor: pointer
      &:last-child
        margin-right: 0
      dt
        height: 300px
        img
          width: 100%
      dd
        margin-top: 30px
        h3
          font-size: 18px
          font-weight: bold
          text-align: center
          ellipsis()
        time
          color: #ccc
          display: block
          text-align: center
          margin: 10px 0
        p
          color: #ccc
          line-height: 18px
          height: 36px
          overflow: hidden
          text-overflow: ellipsis
</style>
