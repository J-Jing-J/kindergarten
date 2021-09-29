<template>
	<view class="">
		<view class="title">
			<view class="address" v-for="(item,index) in rightslist" :key="index">
				<view class="message">
					<image :src="item.imgUrl" mode=""></image>
					<text class="name">{{item.name}}</text>
				</view>

				 <view class="rights">
					<text class="rightname">{{item.text}}</text>
				 </view>
			</view>
 
		</view>
	</view>
</template>

<script>
	export default {
			data() {
				return {
					 test: [
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "纽约国际儿童俱乐部",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},	{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},	{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},	{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},	{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						{
							imgUrl:require("../../static/Jinx.jpg"),
							name: "杨梅红国际私立美校扬名广场校区",
							text: "暂无权益，敬请期待"
						},
						
					],
				}
			},
			methods: {
 
			},
			props: {
				rightslist: {
					type: Array,
					required: true
				}
			}
		}
	</script>
 

<style scoped lang="scss">
	.title {
		// background-color: #eee;
		.message {
		    display: flex;
			height: 100rpx;
			margin-top: 50rpx;
			border-bottom: 2rpx solid #eee;
			image {
				border-radius: 50rpx;
				width: 80rpx;
				height: 80rpx;
			}
			.name {
				padding-left: 30rpx;
				padding-top: 20rpx;
			}
		}
		.rights {
			padding-top: 20rpx;
			.rightname {
				padding-left: 10rpx;
				color: rgb(145, 141, 140)
			}
		}
	}
</style>
