/* eslint-disable */
<template>
	<el-container>
	  <el-header>Header</el-header>
	  <el-main>
	  	<el-form :model="ruleForm" :rules="rules" ref="ruleForm"  class="demo-ruleForm">
			  <el-form-item label="用户名" prop="username">
			    <el-input
				  placeholder="请输入用户名"
				  v-model="ruleForm.username"
				  clearable>
				</el-input>
			  </el-form-item>
			  <el-form-item label="密码" prop="password">
			  	<el-input style="width:300px;margin-top: 30px;" placeholder="请输入密码" v-model="ruleForm.password" show-password></el-input>
			  	</el-form-item>
			  	<el-form-item>
			  		<el-button type="primary" @click="submitForm('ruleForm')">立即创建</el-button>
			  	</el-form-item>
	  	</el-form>
	  	
	  </el-main>
	  
	 
	</el-container>
</template>

<script>
	 export default {
	    data() {
	      return{
	      	ruleForm:{
	      		username:'',
	      		password:'',
	      	},
	      	rules:{
	      		username: [
		            { required: true, message: '请输入用户名', trigger: 'blur' },
		          ],
		          password: [
		            { required: true, message: '请输入密码', trigger: 'blur' }
		          ],
	      	},
	      	
	        loading: true
	      }
	    },
	    methods:{
	    	submitForm(formName) {
		        this.$refs[formName].validate((valid) => {
		          if (valid) {
		            alert('submit!');
		          } else {
		            console.log('error submit!!');
		            return false;
		          }
		        });
		      },
	    }
	  };
</script>

<style>
	.el-container{
		height: 100%;
	}
 .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
  }
</style>