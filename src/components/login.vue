<template>
  <div class="container">
  <el-form :model="ruleForm2" :rules="rules2" ref="ruleForm2" label-width="80px" class="eform">
    <div class="login-warp">
      <el-form-item label="用户名" prop="uname">
        <el-input v-model="ruleForm2.uname"></el-input>
      </el-form-item>
      <el-form-item label="密码" prop="pass">
        <el-input type="password" v-model="ruleForm2.pass" auto-complete="off"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="handleLogin">登录</el-button>
        <el-button @click="resetForm('ruleForm2')">取消</el-button>
      </el-form-item>
    </div>
  </el-form>
  </div>
</template>
<script type="text/ecmascript-6">
  export default {
    data() {
      var checkUname = (rule, value, callback) => {
        if (!value) {
          return callback(new Error('请输入用户名'));
        }

      };
      var validatePass = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请输入密码'));
        } else {
          callback();
        }
      };
      return {
        ruleForm2: {
          pass: 'admin',
          uname: 'admin'
        },
        rules2: {
          pass: [
            { validator: validatePass, trigger: 'blur' }
          ],

          uname: [
            { validator: checkUname, trigger: 'blur' }
          ]
        }
      };
    },
    methods: {
      handleLogin() {
        console.time('test');
        this.$router.push({ path: '/Hello' });
        console.timeEnd('test');
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
  }
</script>
<style scoped>
  @media (min-width: 1200px){
    .container {
      width: 1170px;
    }
  }
  @media (min-width: 992px){
    .container {
      width: 970px;
    }
  }
  @media (min-width: 768px){
    .container {
      width: 750px;
    }
  }
  .container {
    margin-right: auto;
    margin-left: auto;
    padding-left: 15px;
    padding-right: 15px;
  }

  .eform{
    max-width: 330px;
    margin: 150px auto;
    background: #fff;
    border-radius: 5px;
    display: block;
    -webkit-border-radius: 5px;
  }
  .login-wrap {
    padding: 20px;
    position: relative;
  }
  .el-input, .el-input__inner{
    width:200px;
  }
</style>
