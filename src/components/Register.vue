<template>
<div id="login-form-container" style="height:100%; padding:0px;">
  <el-form
    :model="ruleForm2"
    :rules="rules2"
    ref="ruleForm2"
    label-position="left"
    label-width="60px"
    class="demo-ruleForm login-container"
    id="login-form"
  >
    <h3 class="title">用户注册</h3>
    <el-form-item prop="account" >
      <el-input style="display:inline" type="text" v-model="ruleForm2.account" auto-complete="off" placeholder="手机号"></el-input>
         <el-link @click="sendVerfy" style="display:inline" type="primary">发送验证码</el-link>
    </el-form-item>
    <el-form-item prop="checkPass">
      <el-input v-model="ruleForm2.checkPass" auto-complete="off" placeholder="验证码"></el-input>
    </el-form-item>
    <!-- <el-checkbox v-model="checked" checked class="remember">记住密码</el-checkbox> -->
    <el-form-item style="width:100%;">
      <el-button
        type="primary"
        style="width:100%;"
        @click.native.prevent="handleSubmit2"
        :loading="logining"
      >登录</el-button>
      <!--<el-button @click.native.prevent="handleReset2">重置</el-button>-->

    </el-form-item>
  </el-form>
  </div>
</template>
<script>
export default {
    name:'Register',
      data() {
    return {
      logining: false,
      ruleForm2: {
        account: "",
        checkPass: ""
      },
      rules2: {
        account: [
          { required: true, message: "请输入账号", trigger: "blur" }
          //{ validator: validaePass }
        ],
        checkPass: [
          { required: true, message: "请输入密码", trigger: "blur" }
          //{ validator: validaePass2 }
        ]
      },
      checked: true
    };
  },
  methods:{
      handleSubmit2(e){
          console.log("==**==");
          this.$router.push("/takeaway");
      },
      sendVerfy(){
        this.ruleForm2.checkPass = '456999';
      }
  }

}
</script>
<style>
</style>