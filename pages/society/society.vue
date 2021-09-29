<template>
	<view class="container1">
		<view class="container2">
			<tag class="tag"></tag>
		</view>
		<view class="container3">
			<speech class="message" @getIcon="getIcon()" :iconList="iconList"></speech>
		</view>
 
		<view class="lab">
			<unifab class="uni-fab"  :content="content" :pattern="pattern" :horizontal="horizontal" :vertical="vertical" :direction="direction"
			 @trigger="trigger"></unifab>
		</view>
 
	</view>
</template>

<script>
	import tag from '../../components/tag/tag.vue'
	import speech from '../../components/speech/speech.vue'

	import unifab from '../../components/uni-fab/uni-fab.vue'
	export default {
		components: {
			tag,
			speech,
			unifab
		},
		data() {
			return {
				iconList: [],
				// url: 'mine/post/post',
				content: [{
					iconPath: '../../static/society/发布的帖子.png',
					text: '发布帖子',
					details: '与邻居分享心情，分享见闻'
				}, {
					iconPath: '../../static/society/帮助.png',
					text: '发布帮助',
					details: '闲置物品，邻里交易更放心'

				}, {
					iconPath: '../../static/society/活动.png',
					text: '发布活动',
					details: '和邻居相约，热闹非凡'

				}],
				pattern: {
					color: '#000000',
					selectedColor: '#007AFF',
					backgroundColor: '#ffffff',
					buttonColor: 'rgb(233, 125, 122)'
				},
				vertical: 'bottom',
				horizontal: 'right',
				direction: 'vertical'
 
			}
		},
		onLoad() {
			this.getIcon()
		},
		methods: {
			getIcon() {
				uni.request({
					url: 'https://api-hmugo-web.itheima.net/api/public/v1/home/swiperdata', //仅为示例，并非真实接口地址。
					success: (res) => {
						this.iconList = res.data.message;
						console.log(this.iconList);
					},
					fail: () => {
						console.log("失败了")
					}
				});
 
			},

		 trigger(e) {
			 console.log(e)
			// let other = this.content.map((d, i) => {
			//    d.active = i== e.index
			// }) //改变悬浮按钮中内容的状态是否为选定
 
			uni.showToast({
				title:'选择了'+this.content[e.index].text
			}) //页面显示用户选择的功能
			 setTimeout(function(){
				 if(e.index === 0) {
					uni.navigateTo({
						url: '/pages/mine/post/post'
					})
				 } 
				 else if(e.index === 1){
					uni.navigateTo({
					 	url: '/pages/mine/friendHands/friendHands'
					})
				 }
				 else{
					uni.navigateTo({
					 	url: '/pages/mine/activities/activities'
					})
				 }
			 },1000)
 
 
			}
		}
	}
	
</script>

<style scoped lang="scss">
	.container1 {
		height: 100vh;
		overflow: hidden;
		background-color: #eee;

		.container2 {
			height: 200rpx;
			margin: 20rpx 20rpx;
			background-color: white;
			border-radius: 20rpx;
		}

		.container3 {
			height: auto;
			margin: 20rpx 20rpx;
			background-color: white;
			border-radius: 20rpx;

			.message {
				padding: 20rpx 30rpx;
			}
		}

 
		.lab {
			height: 300rpx;
			color: red;
			background-color: #E5E5E5;
			// .uni-fab {
			// 	width: 400rpx;
			// 	height: 200rpx;
			// }
		}

 
	}
</style>
