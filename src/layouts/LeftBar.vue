<template>
  <!-- 侧边栏组件:  系统概况 跟交换机 机框1 系统日志 资源管理 用户管理 系统设置 #13c2c2-->
  <a-layout-sider :class="['side-menu', 'shadow']" width="256px" v-model="collapsed"
    :trigger="null">
    <div :class="['logo']">
      <router-link to="/">
        <img src="@/assets/images/logo.png" alt="">
        <h1>{{systemName}}</h1>
      </router-link>
    </div>
    <a-menu theme="dark" mode="inline" :default-selected-keys="['1']" :collapsed="true">
      <a-menu-item key="1">
        <a-icon type="home" />
        <span class="nav-text">系统概况</span>
      </a-menu-item>
      <a-menu-item key="2">
        <a-icon type="video-camera" />
        <span class="nav-text">跟交换机</span>
      </a-menu-item>
      <a-menu-item key="3">
        <a-icon type="border" />
        <span class="nav-text">机框1</span>
      </a-menu-item>
      <a-menu-item key="4">
        <a-icon type="profile" />
        <span class="nav-text">系统日志</span>
      </a-menu-item>
      <a-menu-item key="5">
        <a-icon type="cloud-o" />
        <span class="nav-text">资源管理</span>
      </a-menu-item>
      <a-menu-item key="6">
        <a-icon type="user" />
        <span class="nav-text">用户管理</span>
      </a-menu-item>
      <a-menu-item key="7">
        <a-icon type="setting" />
        <span class="nav-text">系统设置</span>
      </a-menu-item>
    </a-menu>
  </a-layout-sider>
</template>

<script>
export default {
  name: 'LeftBar',
  props: ['collapsed'],
  data () {
    return {
      systemName: '智能监控管理系统'
    }
  }
}

</script>

<style lang="scss" scoped>
  .shadow {
    box-shadow: 2px 0 6px rgba(0, 21, 41, .35);
  }

  .side-menu {
    min-height: 100vh;
    overflow-y: auto;
    z-index: 10;

    .logo {
      height: 64px;
      position: relative;
      line-height: 64px;
      padding-left: 20px;
      transition: all .3s;
      overflow: hidden;
      background-color: #053434;

      h1 {
        color: #fff;
        font-size: 20px;
        margin: 0 0 0 12px;
        display: inline-block;
        vertical-align: middle;
      }

      img {
        width: 40px;
      }
    }
  }

</style>
