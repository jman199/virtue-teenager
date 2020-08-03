<template>
	<view class="login">
		<image src="../../static/login-img/blackboard.jpg" class="background"></image>
		<view class="body">
			<view class="header"><text>家长登录</text></view>
			<form @submit="">
				<view class="login-input">
					<view class="input-phonenumber">
						<text>账号：</text>
						<input v-model="username" type="number"  placeholder="请输入手机号" placeholder-style="color:#aaaaaa;font-size:12upx" />
					</view>
					<view class="input-password">
						<text>密码：</text>
						<input v-model="password" type="text" password placeholder="请输入密码" placeholder-style="color:#aaaaaa;font-size:12upx" />
					</view>
				</view>
				<view class="check">
					<label>
						<checkbox checked="true" />
						<text>自动登录</text>
					</label>
					<navigator url="/pages/login/password">忘记密码</navigator>
				</view>
				<view class="login-button">
					<navigator url="/pages/login/register">注册</navigator>
					<t-button :disabled="isDisabled" @click="clickeven">登录</t-button>
				</view>
			</form>
		</view>
	</view>
</template>

<script>
import tButton from "../../components/t-button/t-button.vue"
export default {
	components:{
		tButton
	},
	data() {	
		return {
			username: '',
			password: ''
		};
	},
	watch: {},
	methods: {
		clickeven(){
			uni.navigateTo({
				url:"../index/index"
			})
		}
	},
	computed:{
		isDisabled(){
			//按钮启用禁用状态
			if(this.username&&this.password){
				return false;
			}else{
				return true
			}
		}
	}
};
</script>

<style>
	@font-face {
		font-family:FZY4JW;
		src: url(../../static/font/FZY4JW.TTF);
	}
	.login {
		width: 100%;
		height: 100%;
		/* background-image: url(../../static/login-img/blackboard.jpg);
		background-repeat:no-repeat;
		background-attachment:fixed;
		background-size:100%; */
		font-family:FZY4JW;
		font-size: 18upx;
		color: #ffffff;
	}
.background {
	position: absolute;
	width: 100%;
	height: 100%;
	z-index: -1;
}

.body {
	font-size: 18upx;
	color: #ffffff;
	height: 100%;
	width: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	
}
form {
	width: 100%;
	padding-top: 5%;
}
input {
	border: 2upx solid #ffffff;
	border-radius: 8upx;
	height: 35upx;
	width: 54%;
	text-indent:16upx;
}

checkbox {
	transform: scale(0.6);
}
.login-button {
	display: flex;
	align-items: center;
	justify-content: center;
	margin: 2% 35% ;
}

.input-phonenumber,
.input-password {
	display: flex;
	align-items: center;
	justify-content: center;
	margin: 3% 0;
}
.header {
	justify-self: center;
	margin-top: 2.4%;
	font-size: 22upx;
}
.check {
	width: 100%;
	display: flex;
	justify-content: space-around;
	font-size: 16upx;
	color: #dddddd;
}
</style>
