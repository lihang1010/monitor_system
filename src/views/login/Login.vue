<template>
  <div class="login-container">
    <div class="login-form">
      <h3 class="login-title">智能机监控管理系统</h3>
      <a-form-model ref="loginForm" :model="loginForm" :rules="rules">
        <a-form-model-item ref="username" prop="username">
          <a-input size="large" v-model="loginForm.username" placeholder="请输入用户名" @blur="
          () => {
            $refs.username.onFieldBlur();
          }
        " />
        </a-form-model-item>
        <a-form-model-item prop="password">
          <a-input size="large" type="password" v-model="loginForm.password" placeholder="请输入密码" />
        </a-form-model-item>
        <a-form-model-item label="记住密码" prop="rememberMe" :colon=false style="display: flex;">
          <a-switch v-model="loginForm.rememberMe" />
        </a-form-model-item>
        <a-form-model-item>
          <a-button type="primary" size="large" block @click="onSubmit('loginForm')">登录</a-button>
        </a-form-model-item>
      </a-form-model>
    </div>
    <div class="footer">
      {{copyright}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      loginForm: {
        username: '',
        password: '',
        rememberMe: false
      },
      rules: {
        username: [{
          required: true,
          message: '请输入用户名',
          trigger: 'blur'
        }],
        password: [{
          required: true,
          message: '请输入密码',
          trigger: 'blur'
        }]
      },
      copyright: 'Copyright © 2021. All Rights Reserved. Coded by lihang!'
    }
  },
  methods: {
    onSubmit (formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          alert('submit!')
          window.location.href = '/'
        } else {
          console.log('error submit!!')
          return false
        }
      })
    },
    resetForm (formName) {
      this.$refs[formName].resetFields()
    }
  }
}

</script>

<style lang="scss" scoped>
  .login-container {
    width: 100%;
    height: 100%;
    background: url(../../assets/images/bk.jpg) no-repeat;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;

    .login-form {
      width: 400px;
      border-radius: 6px;
      background: #fff;
      padding: 40px 25px 5px 25px;

      .login-title {
        font-size: 24px;
        letter-spacing: 2px;
        color: #707070;
        text-align: center;
        margin: 0 auto 30px auto;
      }

      .login-btn,
      .reset-btn {
        width: 48.5%;
      }
    }

    .footer {
      width: 100%;
      height: 40px;
      line-height: 40px;
      position: fixed;
      bottom: 0;
      text-align: center;
      color: #fff;
      font-size: 14px;
      letter-spacing: 1px;
    }
  }

</style>
