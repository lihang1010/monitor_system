<template>
  <a-layout-header :class="['header']">
    <div class="header-content">
      <a-icon class="trigger" :type="collapsed ? 'menu-unfold': 'menu-fold'" @click="toggleCollapse"></a-icon>
      <div class="header-right">
        <a-tooltip title="源码地址" class="header-item">
          <a href="https://github.com/lihang1010/monitor_system/tree/master" target="_blank">
            <a-icon type="github"></a-icon>
          </a>
        </a-tooltip>
        <a-dropdown class="header-item">
          <div class="header-avatar" style="cursor: pointer">
            <a-avatar class="avatar" size="small" shape="circle" :src="user.avatar" />
            <span class="name">{{user.name}}</span>
          </div>
          <a-menu :class="['avatar-menu']" slot="overlay">
            <a-menu-item>
              <a-icon type="user" />
              <span>个人中心</span>
            </a-menu-item>
            <a-menu-item>
              <a-icon type="setting" />
              <span>设置</span>
            </a-menu-item>
            <a-menu-divider />
            <a-menu-item @click="logout">
              <a-icon style="margin-right: 8px;" type="poweroff" />
              <span>退出登录</span>
            </a-menu-item>
          </a-menu>
        </a-dropdown>
      </div>
    </div>
  </a-layout-header>
</template>

<script>
export default {
  name: 'HeaderNav',
  props: ['collapsed'],
  data () {
    return {
      user: {
        name: 'Admin',
        avatar: 'https://gitee.com/lihang1209/PicBed/raw/master/touxiang01.jpg'
      }
    }
  },
  methods: {
    toggleCollapse () {
      this.$emit('toggleCollapse')
    }
  }
}

</script>

<style lang="scss" scoped>
  .header {
    width: 100%;
    overflow: hidden;
    background: #fff;

    .header-content {
      width: 100%;
      height: 64px;
      line-height: 64px;

      .trigger {
        font-size: 20px;
        vertical-align: middle;
        transition: color .3s;

        &:hover {
          color: #13c2c2;
        }
      }

      .header-right {
        display: flex;
        float: right;

        .header-item {
          padding: 0 12px;
          align-self: center;

          &:hover {
            background: rgba(0, 0, 0, 0.025);
          }

          .avatar {
              margin-right: 8px;
          }
          .name {
              font-weight: 700;
          }
        }
      }
    }
  }

</style>
