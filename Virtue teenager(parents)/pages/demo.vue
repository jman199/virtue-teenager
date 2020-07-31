<template>
	<view class="main">
		<view class="item1">514</view>
		<view class="item1">2</view>
		<view class="item1">3</view>
		<view class="item1">4</view>
		<view class="item1">5</view>
		<view class="item1">6</view>

	</view>
	
</template>

<script>
</script>

<style>
	.main {
		display: grid;
		width: 600px;
		height: 200px;
		/* border: 10px solid #2C405A; */
		grid-template-columns:100px;
		/* grid-template-rows: 100px; */
		gap: 20px;
		/* grid-template-areas: 'a b c' 'd e f' 'g h i'; */
		justify-content: center;
		justify-items:center;
		align-items: center;
		font-size: 20px;
		
	}
	.main>view:nth-child(odd){
		background: #DDDDDD;
	}
	.main>view:nth-child(even){
		background: #999999;
	}
	.item1 {
		grid-column:1 / 3;
		
		/* width: 100px; */
	}
</style>
