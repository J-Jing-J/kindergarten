<template>
	<view>
		<view class="container">
			<view class="foodTop" v-for="top in tops" :key="top.id">{{top.name}}</view>
			<view class="food" v-for="food in foods" :key="food.id">{{food.name}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				foods: [
					{
						name: '茄子米糊',
						id: 0,
					},
					{
						name: '茄子米糊',
						id: 1
					},
					{
						name: '莲藕胡萝卜',
						id: 2
					},
					{
						name: '水果大杂烩',
						id: 3
					},
					{
						name: '西柚汁',
						id: 4
					},
					{
						name: '胡萝卜肉末',
						id: 5
					},
					{
						name: '豆腐糙米粥',
						id: 5
					},
					{
						name: '茄子米糊',
						id: 0,
					},
					{
						name: '茄子米糊',
						id: 1
					},
					{
						name: '莲藕胡萝卜',
						id: 2
					},
					{
						name: '水果大杂烩',
						id: 3
					},
					{
						name: '西柚汁',
						id: 4
					},
					{
						name: '胡萝卜肉末',
						id: 5
					},
					{
						name: '豆腐糙米粥',
						id: 5
					},
					{
						name: '茄子米糊',
						id: 0,
					},
					{
						name: '茄子米糊',
						id: 1
					},
					{
						name: '莲藕胡萝卜',
						id: 2
					},
					{
						name: '水果大杂烩',
						id: 3
					},
					{
						name: '西柚汁',
						id: 4
					},
					{
						name: '胡萝卜肉末',
						id: 5
					},
					{
						name: '豆腐糙米粥',
						id: 5
					},
					{
						name: '茄子米糊',
						id: 0,
					},
					{
						name: '茄子米糊',
						id: 1
					},
					{
						name: '莲藕胡萝卜',
						id: 2
					},
					{
						name: '水果大杂烩',
						id: 3
					},
					{
						name: '西柚汁',
						id: 4
					},
					{
						name: '胡萝卜肉末',
						id: 5
					},
					{
						name: '豆腐糙米粥',
						id: 5
					},
					{
						name: '胡萝卜肉末',
						id: 5
					},
					{
						name: '豆腐糙米粥',
						id: 5
					},
					{
						name: '茄子米糊',
						id: 0,
					},
					{
						name: '茄子米糊',
						id: 1
					},
					{
						name: '莲藕胡萝卜',
						id: 2
					},
					{
						name: '水果大杂烩',
						id: 3
					},
					{
						name: '西柚汁',
						id: 4
					}
				],
				tops: [
					{
						name: '周一',
						id: 0,
					},
					{
						name: '周二',
						id: 1,
					},
					{
						name: '周三',
						id: 2,
					},
					{
						name: '周四',
						id: 3,
					},
					{
						name: '周五',
						id: 4,
					}
				]
			};
		}
	}
</script>

<style scoped lang="scss">
	.container {
		margin-top: 20rpx;
		width: 100%;
		display: flex;
		justify-content: flex-start;
		align-items: flex-start;
		margin-left: 50%;
		transform: translate(-50%);
		flex-wrap: wrap;
		text-align: center;
	}
	.foodTop {
		width: 20%;
		height: 50rpx;
	}
	.food {
		width: 20%;
		height: 100rpx;
	}
	.food:nth-child(even){
		background-color: #f8a5c2;
	}
	.food:nth-child(odd){
		background-color: #f7d794;
	}
</style>
