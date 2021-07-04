<template>
  <a-layout class="container">
    <left-bar :collapsed="collapsed"></left-bar>
    <a-layout>
      <header-nav :collapsed="collapsed" @toggleCollapse="toggleCollapse"></header-nav>
    </a-layout>
  </a-layout>
</template>

<script>
import LeftBar from '@/layouts/LeftBar'
import HeaderNav from '@/layouts/HeaderNav'

export default {
  name: 'Dashboard',
  components: {
    LeftBar,
    HeaderNav
  },
  data () {
    return {
      collapsed: false
    }
  },
  methods: {
    toggleCollapse () {
      this.collapsed = !this.collapsed
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
