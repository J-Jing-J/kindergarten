<template>
	<view class="home">
		<index-nav-bar></index-nav-bar>
		<view class="swiper">
			<swiper indicator-dots circular autoplay>
				<swiper-item v-for="(item, index) in swiper" :key="index">
					<image :src="item.image"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="functions">
			<functions @goLink="goLink"></functions>
		</view>
		<view class="notice">
			<notice @goDetails="goDetails"></notice>
		</view>
	</view>
</template>

<script>
	import indexNavBar from '../../components/index/indexNavBar/indexNavBar.vue'
	import functions from '../../components/index/functions/functions.vue'
	import notice from '../../components/notice/notice.vue'
	export default {
		data() {
			return {
				HomeData: null,
				swiper: [
					{
						"image": "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Ftxt39-1.book118.com%2F2018%2F0629%2Fbook175765%2F175764018.jpg&refer=http%3A%2F%2Ftxt39-1.book118.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624711499&t=0837ade5812a4f9444ce83225a5362a0",
						"width923": 750,
						"height923": 390,
						"link": "https://act.mogujie.com/huanxin0001?acm=3.mce.2_10_1jhwa.43542.0.ccy5br4OlfK0Q.pos_0-m_454801-sd_119",
						"width": 750,
						"acm": "3.mce.2_10_1jhwa.43542.0.ccy5br4OlfK0Q.pos_0-m_454801-sd_119",
						"title": "",
						"height": 390
					},
					{
						"image": "https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2170815659,3875768603&fm=26&gp=0.jpg",
						"width923": 750,
						"height923": 390,
						"link": "https://act.mogujie.com/ruqiu00001?acm=3.mce.2_10_1ji16.43542.0.ccy5br4OlfK0R.pos_1-m_454889-sd_119",
						"width": 750,
						"acm": "3.mce.2_10_1ji16.43542.0.ccy5br4OlfK0R.pos_1-m_454889-sd_119",
						"title": "",
						"height": 390
					},
					{
						"image": "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=3879338485,1091944277&fm=26&gp=0.jpg",
						"width923": 750,
						"height923": 390,
						"link": "https://act.mogujie.com/huanxin0001?acm=3.mce.2_10_1jhwa.43542.0.ccy5br4OlfK0Q.pos_0-m_454801-sd_119",
						"width": 750,
						"acm": "3.mce.2_10_1jhwa.43542.0.ccy5br4OlfK0Q.pos_0-m_454801-sd_119",
						"title": "",
						"height": 390
					},
					{
						"image": "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fdingyue.ws.126.net%2F2020%2F0521%2F4188738ej00qaody40019c000rs00dzc.jpg&refer=http%3A%2F%2Fdingyue.ws.126.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624711998&t=bc51eeef85cfbd98f9cd10e0f0073551",
						"width923": 750,
						"height923": 390,
						"link": "https://act.mogujie.com/huanxin0001?acm=3.mce.2_10_1jhwa.43542.0.ccy5br4OlfK0Q.pos_0-m_454801-sd_119",
						"width": 750,
						"acm": "3.mce.2_10_1jhwa.43542.0.ccy5br4OlfK0Q.pos_0-m_454801-sd_119",
						"title": "",
						"height": 390
					},
				],
				max: 50,
			}
		},
		components: {
			indexNavBar,
			functions,
			notice,
		},

		created() {},
		
		methods: {
			login() {
				uni.login({
				  provider: 'weixin',
				  success: res => {
				    console.log(res);
				  }
				});
			},
			goLink(url, index) {
				uni.navigateTo({ url })
			},
			goDetails(url) {
				uni.navigateTo({ url })
			},
			goUsersright(url) {
				uni.navigateTo({ url })
			},
			goServiceplan(url) {
				uni.navigateTo({ url })
			},
		},
	}
</script>

<style scoped lang="scss">
	.home {
		height: 100vh;
		background-color: #f0f0f0;

		swiper {
			width: 750rpx;
			height: 380rpx;

			image {
				width: 100%;
				height: 100%;
				margin-top: 70rpx;
			}
		}
		.notice {
			height: 100rpx;
			background-color: white;
		}
		.users-right {
			margin-top: 40rpx;
		}
	}
</style>
