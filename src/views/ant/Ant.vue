<template>
  <div class="login-container">
    <div class="login-form">
      <h3 class="login-title">智能机监控管理系统</h3>
      <!-- <el-form :model="loginForm" :rules="rules" status-icon ref="loginForm" class="login-LoginForm">
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
      </el-form> -->
      <a-form-model ref="loginForm" :model="loginForm" :rules="rules">
        <a-form-model-item ref="username" prop="username">
          <a-input v-model="loginForm.username" placeholder="请输入用户名" @blur="
          () => {
            $refs.username.onFieldBlur();
          }
        " />
        </a-form-model-item>
        <a-form-model-item prop="password">
          <a-input type="password" v-model="loginForm.password" placeholder="请输入密码" />
        </a-form-model-item>
        <a-form-model-item label="记住密码" prop="rememberMe" :colon=false>
          <a-switch v-model="loginForm.rememberMe" />
        </a-form-model-item>
        <a-form-model-item>
          <a-button type="primary" @click="onSubmit('loginForm')">登录</a-button>
          <a-button style="margin-left: 10px;" @click="resetForm('loginForm')">重置</a-button>
        </a-form-model-item>
      </a-form-model>
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
      labelCol: {
        span: 4
      },
      wrapperCol: {
        span: 14
      },
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
      }
    }
  },
  methods: {
    onSubmit (formName) {
      this.$refs[formName].validate(valid => {
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
