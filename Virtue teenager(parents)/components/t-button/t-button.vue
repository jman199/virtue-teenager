<template>
	<view class="t-button">
		<button  :type="type"  :disabled="disabled" @click="$emit('click')">
			<slot></slot>
		</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{				
			}
		},
		props:{
			type:{
				type:String
			},
			disabled:{
				type:Boolean,
				default:false
			}
		},
		
	}
</script>

<style>
	button {
		width: 150upx;
		height: 55upx;
		background-image: url(../../static/login-img/button1.jpg);
		background-size: 100%;
/* 		background-repeat: no-repeat;
		background-position: 0 0; */
		border-radius: 13upx;
		color: #30592d;
		font-weight: bold;
		font-size: 22upx;
		font-family: FZY4JW;
		margin: 0 14upx;
	}
</style>
