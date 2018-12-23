<template>
  <div>
    <common-header/>
    <menu-detail/>
    <common-footer/>
  </div>
</template>

<script>
import CommonHeader from 'common/Header'
import CommonFooter from 'common/Footer'
import MenuDetail from 'common/Menu'

export default {
  name: 'Home',
  components: {
    CommonHeader,
    CommonFooter,
    MenuDetail
  }
}
</script>

<style></style>
