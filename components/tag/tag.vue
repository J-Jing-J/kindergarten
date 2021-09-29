<template>
	<view class="container"> 
		 <view class="activity"> 
			<view :class="[item,number1===index?'active':'']" v-for="(item,index) in list1" :key='index'>
				<text class="tagname" @click="changenumber1(index)">{{item.context}}</text>
			</view>
		 </view> 
		 <view class="area">
			<view :class="[item,number2===index?'active':'']" v-for="(item,index) in list2" :key='index'>
				<text class="tagname" @click="changenumber2(index)">{{item.context}}</text>
			</view>
		 </view> 
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tagname:"tagname",
				number1:0,
				number2:0,
				list1: [
					{id: 0,context: '全部记录'},
					{id: 1,context: '观察记录'},
					{id: 2,context: '轶事记录'},
					{id: 3,context: '学习故事'},
				],
				list2: [
					{id: 0,context: '健康'},
					{id: 1,context: '语言'},
					{id: 2,context: '社会'},
					{id: 3,context: '科学'},
					{id: 3,context: '艺术'},
				]
			}
	 
		},
		methods:{
			 changenumber1(index){
				 this.number1 = index
			 },		
		     changenumber2(index){
				 this.number2 = index
			 }
			 
		}
	}
</script>

<style>
	.container {
/* 		height: 200rpx;
		background-color: white; */
	},
	.activity {
		display: flex;
		padding: 20rpx;
	},
	.area {
		display: flex;
		margin-top: 20rpx;
		padding-left: 20rpx;
	},

	.tagname {
		font-size: 20rpx;
		font-weight: 600;
		padding: 0rpx 10rpx;
	/* 	height: 20px; */
		line-height: 50rpx;
/* 		margin: 0 10rpx;
		border-radius: 30rpx; */
	}
	.item {
		margin: 0 10rpx;
		border-radius: 30rpx;
	}
	.active {
		margin: 0 10rpx;
		border-radius: 30rpx;

		background-color: #ffb8b8;
	}
</style>
