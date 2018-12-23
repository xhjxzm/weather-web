<template>
  <div class="footer">
    <div class="footer-link">
      <a href="">升级日志</a>
      <span></span>
      <a href="">常见问题</a>
      <span></span>
      <a href="">设计师平台</a>
      <span></span>
      <a href="">服务协议</a>
    </div>
    <div class="address">
      <p>公司地址：北京市西城区区西山桥路56号爱基大厦A1区1门c616 联系电话：311-113-3113</p>
      <p>Copyright © 2008-2018北京CK股份有限公司 All Right Reserved</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonFooter'
}
</script>

<style lang="stylus">
.footer
  margin-top: 70px
  text-align: center
  color: #959699
  font-size: 12px
  .footer-link
    margin-bottom: 30px
    a
      color: #30343f
      font-size: 14px
    span
      display: inline-block
      width: 1px
      height: 18px
      background: #e0e1e3
      margin: 0 16px
      vertical-align: -4px
  .address
    line-height: 24px

</style>
