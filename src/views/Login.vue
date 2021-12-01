<template>
  <div class="logincontiner">
    <el-form
        :rules="rules"
        :model="userForm"
        ref="userForm"
        :inline="false"
        size="medium"
        class="loginForm">
      <el-form-item>
        <div class="loginTitle">系统登录</div>
      </el-form-item>
      <el-form-item prop="username">
        <el-input placeholder="请输入用户名" v-model="userForm.username"></el-input>
      </el-form-item>
      <el-form-item prop="password">
        <el-input placeholder="请输入密码" v-model="userForm.password"></el-input>
      </el-form-item>
      <el-form-item prop="code">
        <el-row :gutter="20">
          <el-col :span="16">
            <el-input v-model="userForm.code"
                      placeholder="请输入验证码"></el-input>
          </el-col>
          <el-col :span
                      ="8"> <!-- <img class="codeimg"> -->
            <el-input  v-model="userForm.code" placeholder="请输入验证码" readonly></el-input>
          </el-col>
        </el-row>
      </el-form-item>
      <el-form-item>
        <el-row :gutter="20">
          <el-col :span="12">
            <el-button type="primary" size="default" class="btn" @click="commitBtn">登录</el-button>
          </el-col>
          <el-col :span="12">
            <el-button size="default" class="btn" @click="resetBtn">重置</el-button>
          </el-col>
        </el-row>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      userForm:
          {
            username: "",
            password: "",
            code: "",
          },
      rules: {
        username: [
          {required: true, message: '请输入用户名', trigger: 'blur'}
        ],
        password: [
          {required: true, message: '请输入密码', trigger: 'blur'}
        ],
        code: [
          {required: true, message: '请输入验证码', trigger: 'blur'},
          {min: 5, max: 5, message: '验证码为5个字符', trigger: 'blur'}
        ],
      },
    }
  },
  methods:{
    commitBtn(){
      this.$refs.userForm.validate(valid => {
        if (valid){
          console.log("valid:--+"+valid)
        }
      })
    },
    resetBtn(){
      this.$refs['userForm'].resetFields();
    }
  }
}
</script>

<style scoped>
.logincontiner {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.loginForm {
  height: 300px;
  width: 350px;
  border-radius: 10px;
  box-shadow: 0 0 25px #cac6c6;
  padding: 20px 35px;
}

.loginTitle {
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: 600;
  font-size: 24px;
}

.codeimg {
  border: 1px solid #dcdfe6;
  cursor: pointer;
}

.btn {
  width: 100%;
}

</style>
