<template>
	<view class="context">
		<view class="title">
			<text class="word">物业公告<span style="padding-left: 30rpx;font-weight: 100">|</span></text>
		</view>
		<view class="notice">
			<text class="word" @click="goDetails(url)">查看往期公告<span>>>></span></text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				url: 'notice/notice'
			};
		},
		methods: {
			goDetails(url) {
				this.$emit('goDetails', url);
			}
		}
	}
</script>

<style lang="scss" scoped>
	.context {
		display: flex;

		.title {
			margin: 20rpx 50rpx;
			font-size: 38rpx;
			font-weight: bold;

			.word {
				font-weight: bold;
			}
		}

		.notice {
			margin-top: 28rpx;
			margin-left: 150rpx;
			font-size: 30rpx;
			color: red;
		}
	}
</style>
