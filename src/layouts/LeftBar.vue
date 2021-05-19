<template>
  <div class="bar">
    <div class="logo-container">
      <router-link to="/" class="logo">
        <img src="@/assets/images/logo.png" alt="">
        <h3>监控管理系统</h3>
      </router-link>
    </div>
    <div class="nav">
      <el-menu default-active="2" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose"
        background-color="#032121" text-color="rgba(254, 254, 254, 0.65)" active-text-color="#fff">
        <el-menu-item index="2">
          <i class="el-icon-s-home"></i>
          <span slot="title">系统概况</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">跟交换机</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">机框1</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">机框2</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">机框3</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">机框4</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">系统日志</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">资源管理</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">用户管理</span>
        </el-menu-item>
        <el-menu-item index="3">
          <i class="el-icon-document"></i>
          <span slot="title">系统设置</span>
        </el-menu-item>
      </el-menu>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LeftBar'
}

</script>

<style lang="scss" scoped>
  a {
    text-decoration: none;
  }

  .bar {
    width: 256px;
    height: 100%;
    background-color: #032121;

    .logo-container {
      width: 100%;
      height: 64px;
      background-color: #053434;

      .logo {
        width: 90%;
        height: 64px;
        display: flex;
        align-items: center;
        justify-content: space-around;
        overflow: hidden;

        img {
          width: 40px;
          height: 40px;
        }

        h3 {
          font-size: 20px;
          font-weight: 600;
          font-family: Avenir, "Microsoft YaHei", Helvetica;
          letter-spacing: 1px;
          color: #fff;
        }
      }
    }

    .nav {
      width: 100%;
      // height: calc(100% - 64px);
    }
  }

</style>
