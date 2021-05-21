<template>
  <a-layout class="container">
    <left-bar></left-bar>
  </a-layout>
</template>

<script>
import LeftBar from '@/layouts/LeftBar'

export default {
  name: 'Dashboard',
  components: {
    LeftBar
  },
  data () {
    return {
      collapsed: false
    }
  }
}
</script>

<style lang="scss" scoped>
  .container {
    width: 100%;
    height: 100%;
  }
</style>
