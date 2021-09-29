<template>
	<view class="homeServices">
		<top-bar @topClick="topClick" ref="topbar"></top-bar>
		<scroll-view class="goodsScro" scroll-y @scroll="scroll" enable-back-to-top scroll-with-animation>
			<goods-list :goods="showGoods"></goods-list>
		</scroll-view>
		<u-back-top :scroll-top="scrollTop" :icon-style="iconStyle" :bottom="130" :top="600"></u-back-top>
	</view>
</template>

<script>
	import mSearch from '../../../components/homeServices/mehaotian-search/mehaotian-search.vue'
	import topBar from '../../../components/homeServices/topbar/topbar.vue'
	import GoodsList from '../../../components/homeServices/goods/GoodsList.vue'
	export default {
		data() {
			return {
				goods: {
					'pop': {
						page: 0,
						list: [
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinacn%2Fw600h400%2F20171220%2Ff4ac-fypvuqe2900097.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624800603&t=0c59c49006701157cfeada13a796dca4',
								title: '孩子脾气暴躁怎么办'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fimages%2F20190627%2Fd17073eaa85945b38aaa7fb863a3234c.jpeg&refer=http%3A%2F%2F5b0988e595225.cdn.sohucs.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624800675&t=8028d002b4196c3b8ade8d7d175b47ec',
								title: '这几种透支亲子关系的做法。。'
							},
							{
								image: 'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2272082642,229517519&fm=26&gp=0.jpg',
								title: '孩子看电视的危害'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimage.xinli001.com%2F20140621%2F111138%2F713562.jpg&refer=http%3A%2F%2Fimage.xinli001.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624714829&t=58e7b226a0965613d1141bbc14d9df2f',
								title: '太管事的家长，孩子往往不懂事'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201511%2F09%2F20151109111448_usGKP.thumb.700_0.jpeg&refer=http%3A%2F%2Fb-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624800744&t=61c47425fe8009147cffc0367df2a540',
								title: '一个家庭不幸福。这件小事会暴露'
							},
							{
								image: 'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2856153875,1712562181&fm=26&gp=0.jpg',
								title: '孩子个性发展'
							},
							{
								image: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2233509555,2924466630&fm=26&gp=0.jpg',
								title: '孩子好习惯养成'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fwww.t-chs.com%2FtuhsJDEwLmFsaWNkbi5jb20vYmFvL3VwbG9hZGVkL2kzLzMyOTI2ODM2NTAvVEIybVNHX2xuZFlCZU5rU21MeVhYWGZuVlhhXyEhMzI5MjY4MzY1MCQ5.jpg&refer=http%3A%2F%2Fwww.t-chs.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624800977&t=b06f0f7852625d7904c90d42094d290e',
								title: '孩子不懂事怎么办'
							}
						]
					},
					'new': {
						page: 0,
						list: [
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fwww.t-chs.com%2FtuhsJDEwLmFsaWNkbi5jb20vaTMvMjQ4NTI1MDI4NS9PMUNOMDE5MFduYmsxRHlaTU9FenNBTF8hITI0ODUyNTAyODUkOQ.jpg&refer=http%3A%2F%2Fwww.t-chs.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624800872&t=c79e557f745c485099d204515c83dccd',
								title: '1231233'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinacn%2Fw534h499%2F20180313%2F711b-fyscsmu9973530.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624801056&t=59533ef37c271a67376c1e30148b3429',
								title: '1231233'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Ftao.goulew.com%2Fusers%2Fupfile%2F20191207%2F8e567af2-c0fa-49a7-9483-8cdd565d49e6.jpg&refer=http%3A%2F%2Ftao.goulew.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624801083&t=fff56bf4355e66a4aedf8c0b2c654ee6',
								title: '1231233'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinacn15%2F223%2Fw518h505%2F20180826%2F98cd-hifuvph0736171.jpg&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624801106&t=ac813b39dc19aef30f7b4ffe5a5e4f11',
								title: '1231233'
							},
							{
								image: 'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1615938223,2567566941&fm=26&gp=0.jpg',
								title: '1231233'
							},
							{
								image: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=321635256,3056380680&fm=26&gp=0.jpg',
								title: '1231233'
							},
							{
								image: 'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=3192886862,1556360187&fm=26&gp=0.jpg',
								title: '1231233'
							},
							{
								image: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg3.duitang.com%2Fuploads%2Fitem%2F201608%2F23%2F20160823155507_8QAhH.jpeg&refer=http%3A%2F%2Fimg3.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624801234&t=45ad9a97cee0459a1b8c6cdff48dc75f',
								title: '1231233'
							},
						]
					}
				},
				currentType: 'pop',
				id: 0,
				scrollTop: 0,

				iconStyle: {
					color: '#ff0000',
				}
			}
		},
		components: {
			mSearch,
			topBar,
			GoodsList,
		},
		created() {},
		computed: {
			showGoods() {
				return this.goods[this.currentType].list
			}
		},
		onReachBottom() {
			this.goods[this.currentType].page++;
		},
 
		methods: {
			// 搜索框
			search(e, val) {
				console.log(e, val);
				this['val' + val] = e;
			},
			
			goShoppingCart() {
				uni.navigateTo({
					url: '../../shoppingCart/shoppingCart'
				})
			},
				
			
			// 监听topbar被点击
			topClick(index) {
				switch (index) {
					case 0:
						this.currentType = 'pop'
						break
					case 1:
						this.currentType = 'new'
						break
				}
				this.$refs.topbar.currentIndex = index;
			},
			// 返回顶部
			onPageScroll(e) {
				this.scrollTop = e.scrollTop;
			},
			
		}
	}
</script>

<style scoped lang="scss">
	.homeServices {
		background-color: #f0f0f0;
		.goods {
			display: flex;
			flex-wrap: wrap;
			flex-direction: row;
			justify-content: space-around;
			padding: 2px;

		}



	}
</style>
