<template>
	<view class="container">
		<view class="getDate">
			<text>选择学期</text>
			<text style="padding-left:80rpx">当前选择:</text>
			<picker @change="bindPickerChange" :value="index" :range="yearArray">
			    <view class="uni-input">{{yearArray[index]}}</view>
			</picker>
		</view>
		<view class="getDate activity">
			<text>参加活动</text>
			<text style="padding-left:80rpx">暂无</text>
		</view>
		
		
	</view>
</template>


<script>
export default {
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
	.container {
		margin-top: 20px;
	}
	.commit {
		padding-left: 660rpx;
		margin: 20rpx 0px;
		color: red;
	}
	.box {
		height: 300rpx;
		margin: 10rpx 20rpx;
		background-color: rgb(249, 249, 249);
		border-radius: 10rpx;
	}
	.context {
		padding: 10rpx 20rpx;
	}
	.choice1 {
		padding: 40rpx 20rpx;
		border-bottom: solid 1px #eee;
	}

	.getDate {
		background-color: #f7d794;
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
	.activity {
		height: 1000px;
		background-color: #f3a683;
	}
</style>
