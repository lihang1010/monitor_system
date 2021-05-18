<template>
  <div class="login-container">
    <div class="login-form">
      <h3 class="login-title">智能机监控管理系统</h3>
      <el-form :model="loginForm" :rules="rules" status-icon ref="loginForm" class="login-ruleForm">
        <el-form-item prop="username">
          <el-input v-model="loginForm.username" type="text" autocomplete="off" placeholder="请输入用户名"></el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input v-model="loginForm.password" type="password" autocomplete="off" placeholder="请输入密码"></el-input>
        </el-form-item>
        <el-form-item label="记住密码">
          <el-switch v-model="loginForm.rememberMe"></el-switch>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('loginForm')" class="login-btn">登录</el-button>
          <el-button @click="resetForm('loginForm')" class="reset-btn">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
    <div class="footer">
      Copyright © 2021. All Rights Reserved. Coded by lihang!
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
        rememberMe: true
      },
      rules: {
        username: [
          { required: true, message: '请输入用户名', trigger: 'blur' }
        ],
        password: [
          { required: true, message: '请输入密码', trigger: 'blur' }
        ]
      }
    }
  },
  methods: {
    submitForm (formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('submit!')
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
    height: 100vh;
    background: url(../../assets/images/bk.jpg) no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    .login-form {
      width: 400px;
      border-radius: 6px;
      background: #fff;
      padding: 40px 25px 5px 25px;

      .login-title {
        color: #707070;
        text-align: center;
        margin: 0 auto 30px auto;
      }

      .login-btn, .reset-btn {
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
