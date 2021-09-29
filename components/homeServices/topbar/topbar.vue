<template>
	<view class="top-bar">
		<view class="select" v-for="(item, index) in select" @click="isClick(index)" :key="index"
			:class="currentIndex === index? 'active' : '' ">
			{{item}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				currentIndex: 0,
				select: ['家长学堂', '亲子游戏'],
			}
		},
		methods: {
			isClick(index) {
				this.currentIndex = index;
				this.$emit('topClick', index);
			}
		}
	}
</script>

<style scoped lang="scss">
	.top-bar {
		display: flex;
		justify-content: flex-start;
		align-items: center;
		position: fixed;
		width: 100%;
		height: 98rpx;
		line-height: 98rpx;
		background-color: #fff;
		z-index: 9;

		.select {
			// margin-left: 20rpx;
			width: 50%;
			text-align: center;
		}

		.active {
		
			color: #f19066;
			margin-left: 20rpx;
			font-weight: 700;
			border-bottom: 2rpx solid #f19066;
		}
	}
</style>
