<template>
	<view class="menus">
		<uni-list>
			<uni-list-item title="我的素养" :showArrow="true" to="../../pages/mine/order/order"></uni-list-item>
		</uni-list>
		
		<uni-list>
			<uni-list-item title="功能异常与产品建议" :showArrow="true" to="../../pages/mine/problem/problem"></uni-list-item>
			<uni-list-item title="通知设置" :showArrow="true" to="../../pages/mine/setting/setting"></uni-list-item>
			<uni-list-item title="关于我们" :showArrow="true" to="../../pages/mine/ours/ours"></uni-list-item>
		</uni-list>
	</view>
</template>

<script>
	import uniList from './uni-list/components/uni-list/uni-list.vue'
	import uniListItem from './uni-list/components/uni-list-item/uni-list-item.vue'
	export default {
		components: {
			uniList,
			uniListItem,
		}
	}
</script>

<style scoped lang="scss">
	.menus {
		margin-top: 20rpx;
		.uni-list {
			margin-top: 20rpx;
		}
	}
</style>
