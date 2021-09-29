<template>
	<view class="">
		<view class="message"   v-for="(item,index) in iconList" :key="index">
			<view class="user">
				<view class="context1">
					<image class="img" :src="item.image_src" mode=""></image>
				</view>
				<text class="title">{{item.goods_id}}</text>
				<view class="context2">
					<text class="text">{{item.navigator_url}}</text>
				</view>
			</view>
 
		</view>
	</view>
	
</template>

<script>
	export default {
 
		props:['iconList'],
		data() {
			return {
				list: [
					{id: 0,url: '',name: 'Danny',address: '珠海红树海岸'},
					{id: 1,url: '',name: 'Danny',address: '珠海红树海岸'},
					{id: 2,url: '',name: 'Danny',address: '珠海红树海岸'},
				] 
			}
		},
		methods: {
			getIcon(){
				this.$emit("getIcon");
			}
		}
	}
</script>

<style>
	.button{
		width: 70rpx;
		height: 70rpx;
	}
	.img {
		width: 70rpx;
		height: 70rpx;
		border-radius: 50rpx;
		margin-left: 50%;
		transform: translate(-50%);
		margin-top: 10rpx;
	}
	.message {
		background-color: #ffcccc;
	}
	.user {
		width: 100%;
		height: auto;
		background-color: white;
		margin: 50rpx auto;
		border:1px solid #eee;
		border-radius: 20rpx;
 
	}
	.context1 {
		padding: 10rpx 20rpx;
	}
	.context2 {
		margin: 50rpx 20rpx;
	}
	.title {
		font-size: 25rpx;
		font-weight: 600;
		color: #333333;
		width: 100%;
		margin-left: 47%;
	}
	.text {
		font-size: 23rpx;
		font-weight: 400;
		color: #666666;
		width: 100%;
	}
</style>
