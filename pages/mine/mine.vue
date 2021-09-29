<template>
	<view class="mine">
		<top></top>
		<menus></menus>
	</view>
</template>

<script>
	import top from '../../components/mine/top.vue'
	import center from '../../components/mine/center.vue'
	import menus from '../../components/mine/menus.vue'
	export default {
		data() {
			return {
				
			}
		},
		components: {
			top,
			center,
			menus
		},
		methods: {
			
		}
	}
</script>

<style scoped  lang="scss">
	.mine {
		background-color: #f0f0f0;
	}
</style>
