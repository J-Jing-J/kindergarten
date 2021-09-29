<template>
	<view class="container">
		<view class="getDate">
			<text>选择学期</text>
			<text style="padding-left:80rpx">当前选择:</text>
			<picker @change="bindPickerChange" :value="index" :range="yearArray">
			    <view class="uni-input">{{yearArray[index]}}</view>
			</picker>
		</view>
		<view class="container3">
			<speech class="message"  :iconList="iconList"></speech>
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
			const currentDate = this.getDate({
				format: true
			})
            return {
				yearArray: ['2020-2021学年度第一学期', '2020-2021学年度第二学期'],
				weekArray: ['第一周', '第二周', '第三周', '第四周','第五周', '第六周', '第七周', '第八周'],
				index: 0,
				date: '请选择日期',
				time: '请选择时间',
				iconList: [
					{
						"image_src": "https://api-hmugo-web.itheima.net/pyg/banner1.png",
						"open_type": "navigate",
						"goods_id": '科学',
						"navigator_url": "。。。。。"
					},
					{
						"image_src": "https://api-hmugo-web.itheima.net/pyg/banner1.png",
						"open_type": "navigate",
						"goods_id": '健康',
						"navigator_url": "？？？？？？？？？"
					},
					{
						"image_src": "https://api-hmugo-web.itheima.net/pyg/banner1.png",
						"open_type": "navigate",
						"goods_id": '艺术',
						"navigator_url": "#####"
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
        methods:{
			
			bindPickerChange: function(e) {
				console.log('picker发送选择改变，携带值为', e.target.value)
				this.index = e.target.value
			},
			bindDateChange: function(e) {
				console.log(e)
				this.date = e.target.value
			},
			bindTimeChange: function(e) {
				this.time = e.target.value
			},
			getDate(type) {
				// this.flagTime++;
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;
				let day = date.getDate();
	
				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year + 2;
				}
				month = month > 9 ? month : '0' + month;;
				day = day > 9 ? day : '0' + day;
				return `${year}-${month}-${day}`;	
				// if(this.flagTime > 0){
				// 	return `${year}-${month}-${day}`;
				// }
				// else{
				// 	return "请选择日期";
				// }
					
			}
        },
    computed: {
        startDate() {
            return this.getDate('start');
        },
        endDate() {
            return this.getDate('end');
        }
    },
}
</script>

<style scoped lang="scss">
	.container3 {
		margin-top: 0;
	}
	.getDate {
		background-color: #ffcccc;
		border-radius: 10px;
		display: flex;
		padding: 50rpx 20rpx;
		border-bottom: solid 1px #eee;
		.date {
			padding-left: 10rpx;
			.uni-input {
				color: rgb(150, 150, 150)
			}
		}
		.time {
			padding-left: 20rpx;
			.uni-input {
				color: rgb(150, 150, 150)
			}
		}
	}
</style>
