<template>
	<view class="functions">
		<view class="box" v-for="(item, index) in functions" :key="index" @click="goLink(item.url,index)">
			<view class="icon iconfont" :class="item.icon"></view>
			<view class="title">{{item.title}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				functions: [{
						icon: 'icon-lvyou',
						title: '家长学堂',
						url: 'bill/bill'
					},
					{
						icon: 'icon-tiyu',
						title: '宝宝相册',
						url: 'repair/repair'
					},
					{
						icon: 'icon-shenghuo',
						title: '园内记录',
						url: 'vistor/vistor'
					},
					{
						icon: 'icon-youxi',
						title: '宝宝记录',
						url: 'vistor/vistor'
					},
					{
						icon: 'icon-shui',
						title: '获奖记录',
						url: 'water/water'
					},
					{
						icon: 'icon-yuer',
						title: '班级活动',
						url: 'car/car'
					},
					{
						icon: 'icon-lieqi',
						title: '成长季',
						url: 'express/express'
					},
					{
						icon: 'icon-meishi',
						title: '健康记录',
						url: 'renovation/renovation'
					},
					{
						icon: 'icon-tianqi',
						title: '本周食谱',
						url: 'guarantee/guarantee'
					},
					{
						icon: 'icon-qingli',
						title: '宝宝请假',
						url: 'clean/clean'
					},
				]
			};
		},
		methods: {
			goLink(url, index) {
				this.$emit('goLink',url,index);
			}
		}
	}
</script>

<style scoped lang="scss">
	.functions {
		display: flex;
		flex-wrap: wrap;
		margin-top: 20rpx;
		background: rgba(243, 243, 243, 0.4);
		.box {
			width: 95%;
			height: 120rpx;
			text-align: center;
			margin-left: 20rpx;
			margin-top: 20rpx;
			display: flex;
			flex-direction: row;
			justify-content: center;
			align-items: center;
			vertical-align: middle;
			background: #FFFFFF;
			border-radius: 16px;
			.iconfont {
				font-size: 50rpx;
				height: 80%;
				display: flex;
				justify-content: center;
				align-items: center;
			}

			.title {
				font-size: 30rpx;
				font-weight: 700;
				margin-left: 50rpx;
				font-weight: bold;
				line-height: 42px;
				color: #333333;
				
			}
		}
	}
</style>
