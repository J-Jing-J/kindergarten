<template>
	<view class="navBar">
		<view class="title">幼儿成长记</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped lang="scss">
.navBar {
	display: flex;
	position: fixed;
	width: 100%;
	justify-content:center;
	align-items: center;
	font-size: 40rpx;
	border-bottom: 4rpx solid #f6f6f6;
	background-color: #fff;
	z-index: 9;
	.title {
		font-weight: 700;
		font-family:"Microsoft Yahei";
		text-align: center;
	}
}
</style>
