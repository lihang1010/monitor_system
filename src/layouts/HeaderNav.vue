<template>
  <div class="header">
      <div class="left">
          <img src="@/assets/images/logo.png" alt="">
          <h3>监控管理系统</h3>
      </div>
      <div class="right"></div>
  </div>
</template>

<script>
export default {
  name: 'HeaderNav'
}
</script>

<style lang="scss" scoped>
    .header {
        width: 100%;
        height: 60px;
        background: #2b333e;

        .left {
            width: 200px;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: space-around;

            img {
                width: 40px;
                height: 40px;
            }

            h3 {
                font-size: 20px;
                font-weight: 600;
                font-family: Avenir, "Microsoft YaHei", Helvetica;
                letter-spacing: 1px;
            }
        }
    }
</style>
