<template>
	<view class="top">
		<view class="head">
			<image src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=620138949,2844598045&fm=26&gp=0.jpg"></image>
		</view>
		<view class="title">
			<view class="name">小柴</view>
			<view class="location">广东省珠海市香洲区金凤路18号</view>
		</view>
	</view>
</template>

<script>
	export default {

	}
</script>

<style scoped lang="scss">
	.top {
		display: flex;
		justify-content: flex-start;
		margin-top: 20rpx;
		border-bottom: 2rpx solid #e2e2e2;
		background-color: #fff;
		.head {
			padding-left: 40rpx;
			image {
				width: 100rpx;
				height: 100rpx;
				border-radius: 50%;
			}
		}
		.title {
			margin-left: 40rpx;
			.name {
				font-weight: 700;
				font-size: 40rpx;
			}
		}

	}
</style>
