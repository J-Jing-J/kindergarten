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
	import tag from '../../../components/tag/tag.vue'
	import speech from '../../../components/speech/speech.vue'
	import unifab from '../../../components/uni-fab/uni-fab.vue'
	export default {
		components: {
			tag,
			speech,
			unifab
		},
		data() {
			return {
				iconList: [
					{
						"image_src": "https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3155998395,3600507640&fm=26&gp=0.jpg",
						"open_type": "navigate",
						"goods_id": '实录',
						"navigator_url": "自觉排队拿水杯，喝完水后，能自觉整齐的放好水杯"
					},
					{
						"image_src": "https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3155998395,3600507640&fm=26&gp=0.jpg",
						"open_type": "navigate",
						"goods_id": '实录',
						"navigator_url": "去打乒乓球"
					},
					{
						"image_src": "https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=3155998395,3600507640&fm=26&gp=0.jpg",
						"open_type": "navigate",
						"goods_id": '分析',
						"navigator_url": "好"
					}
				],
				// url: 'mine/post/post',
				content: [{
					iconPath: '../../../static/society/发布的帖子.png',
					text: '健康',
				}, 
				{
					iconPath: '../../../static/society/帮助.png',
					text: '语言',
				}, 
				{
					iconPath: '../../../static/society/活动.png',
					text: '社会',
				},
				{
					iconPath: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2188201594,3481121273&fm=26&gp=0.jpg',
					text: '科学',
				},
				{
					iconPath: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fbpic.588ku.com%2Felement_origin_min_pic%2F00%2F85%2F21%2F2456e89031013a0.jpg&refer=http%3A%2F%2Fbpic.588ku.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1624775707&t=46fb67578d9968afc4797bf58d86d00f',
					text: '艺术',
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
		}
		

 
	}
</style>
