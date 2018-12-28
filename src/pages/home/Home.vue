<template>
  <div>
    <common-header/>
    <home-content/>
    <common-footer/>
  </div>
</template>

<script>
import CommonHeader from 'common/Header'
import CommonFooter from 'common/Footer'
import HomeContent from 'pages/home/Content'

export default {
  name: 'Home',
  components: {
    CommonHeader,
    CommonFooter,
    HomeContent
  }
}
</script>

<style></style>
