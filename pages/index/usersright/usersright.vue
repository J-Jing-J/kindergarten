<template>
	
	<view class="message">
		<view class="username">
			江门发达哥
		</view>
		<view class="details">
			无欠缴物业费，可享受商户权益
		</view>
		<view class="icon">
			<image src="../../../static/Jinx.jpg" mode=""></image>
		</view>
<!-- 		 <view class="top-bar">
			<view class="select" v-for="(item, index) in select"  @click="isClick(index)"  :key="index"
				:class="currentIndex === index? 'active' : '' ">
				{{item}}
			</view>
		 </view> -->
		 <view class="choicebar">
		 	<choicebar @choiceClick="getRightslist"></choicebar>
		 </view>
		 <view class="rightlist">
			<rightslist :rightslist="rightslist"></rightslist>
		 </view>
	</view>
 
</template>

<script>
	import rightslist from '../../../components/usersright/rightslist.vue'
	import choicebar from '../../../components/usersright/choicebar.vue'
	export default {
		created() {
			this.rightslist = this.rightslist1
		},
		data() {
			return {
				rightslist:[],
				rightslist1: [
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "纽约国际儿童俱乐部",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},	{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},	{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},	{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},	{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "杨梅红国际私立美校扬名广场校区",
						text: "暂无权益，敬请期待"
					},
					
				],
				rightslist2: [
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "111",
						text: "暂无权益，敬请期待"
					},	{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "111",
						text: "暂无权益，敬请期待"
					},
					{
						imgUrl:require("../../../static/Jinx.jpg"),
						name: "111",
						text: "暂无权益，敬请期待"
					},
				],
			}
		},
		methods: {
			getRightslist(index) {
				if(index===0){
					this.rightslist = this.rightslist1
				}
				if(index===1){
					this.rightslist = this.rightslist2
				}
					
			}
		},
		components: {
			rightslist,
			choicebar
		},
	}
</script>

<style scoped lang="scss">
	.message {
		position: relative;
		padding: 20rpx 20rpx;
		height: 300rpx;
		color: rgb(222, 185, 114);
		background-color: rgb(43, 45, 66);
		.username {
			font-size: 40rpx;
			padding-bottom: 20rpx;
		}
		.details {
			font-size: 20rpx;
		}
		.icon {
			position: absolute;
			top: 40rpx;
			right: 80rpx;
			image {
				border-radius: 50rpx;
				width: 80rpx;
				height: 80rpx;
			}
		}
		.choicebar {
			height: 150rpx;
		}
		 .rightlist {
			 margin-top: 20rpx;
		 }
		
	}
 
</style>
