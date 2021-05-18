<template>
  <div class="container">
    <header-nav></header-nav>
    <left-bar></left-bar>
  </div>
</template>

<script>
import HeaderNav from '@/layouts/HeaderNav'
import LeftBar from '@/layouts/LeftBar'

export default {
  name: 'Dashboard',
  components: {
    HeaderNav,
    LeftBar
  }
}
</script>

<style lang="scss" scoped>

</style>
