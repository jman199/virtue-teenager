<template>
	<view class="password">
			<image src="../../static/login-img/back3.png" class="back" @click="backRegister"></image>
			<!-- <image src="../../static/login-img/blackboard.jpg" class="background"></image> -->
			<view class="body">
				<view class="header"><text>找回密码</text></view>
				<form @submit="">
					<view class="login-input">
						<view class="input-phonenumber">
							<text>手机：</text>
							<input v-model="username" type="number" placeholder="请输入手机号" placeholder-style="color:#aaaaaa;font-size:12upx" />
						</view>
						<view class="input-phonenumber">
							<text>密码：</text>
							<input v-model="password" type="text" password placeholder="请输入新密码" placeholder-style="color:#aaaaaa;font-size:12upx" />
						</view>
						<view class="input-password">
							<text>确认：</text>
							<input v-model="password2" type="text" password placeholder="再次输入新密码" placeholder-style="color:#aaaaaa;font-size:12upx" />
						</view>
						<view class="input-password">
							<text>验证码：</text>
							<input class="auth" v-model="authCode" type="text"  placeholder="请输入验证码" placeholder-style="color:#aaaaaa;font-size:12upx" />
							<t-button>获取验证码</t-button>
						</view>
					</view>
			
					<view class="login-button">

						<t-button :disabled="isDisabled" >确认</t-button>
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
				password: '',
				password2: '',
				authCode:''
			}
		},
		computed:{
			isDisabled(){
				if(this.username&&this.password){
					return false;
				}else{
					return true
				}
			}
		},
		methods:{
			backRegister(){
				uni.navigateTo({
					url:"./login"
				})
			}
		}
		}
</script>

<style>
	@font-face {
		font-family:FZY4JW;
		src: url(../../static/font/FZY4JW.TTF);
	}
	.password {
		width: 100%;
		height: 100%;
		background-image: url(../../static/login-img/blackboard.jpg);
		background-repeat:no-repeat;
		background-attachment:fixed;
		background-size:100%;
		font-family:FZY4JW;
		font-size: 18upx;
		color: #ffffff;
	}
		
/* .background {
	position: absolute;
	width: 100%;
	height: 100%;
	z-index: -1;
} */

.body {
/* 	height: 50%;
	width: 100%; */
	display: flex;
	flex-direction: column;
	align-items: center;

}

form {
	width: 100%;
	height: 100%;
	padding-top: 5%;
}
input {
	border: 2upx solid #ffffff;
	border-radius: 8upx;
	height: 35upx;
	width: 54%;
	text-indent:16upx;
}
.back {
	position: fixed;
	width: 8%;
	height: 14%;
}

.login-button {
	display: flex;
	align-items: center;
	justify-content: center;
	/* margin: 10% 35%; */
	margin-bottom: 8%;
/* 	margin-left: 5%; */
}

.input-phonenumber,
.input-password {
	display: flex;
	align-items: center;
	justify-content: center;
	margin: 2% 0;
}
.auth {
	width: 32%;
}
.header {
	justify-self: center;
	margin-top: 2%;
	/* font-weight: bold; */
	font-size: 22upx;
}

</style>
