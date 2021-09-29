<template>
	<view class="">
		<view class="getDate">
			<text>选择学期</text>
			<text style="padding-left:80rpx">当前选择:</text>
			<picker @change="bindPickerChange" :value="index" :range="yearArray">
			    <view class="uni-input">{{yearArray[index]}}</view>
			</picker>
		</view>
		<view class="getDate">
			<text>姓名</text>
			<input class="input-item" value="陶子源"></input>
		</view>
		<view class="getDate">
			<text>生日</text>
			<picker class="time" mode="time" :value="time" start="09:01" end="21:01" @change="bindTimeChange">
			    <view class="uni-input">{{time}}</view>
			</picker>
		</view>
		<view class="getDate">
			<text>身高</text>
			<input class="input-item" value="140"></input>
		</view>
		<view class="getDate">
			<text>体重</text>
			<input class="input-item" value="10kg"></input>
		</view>
		<button class="button">确认更新</button>
		<button class="button">重置信息</button>
		<img class="lineChat" src="../../../static/index/lineChat.jpg" alt="折线图">
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
		display: flex;
		padding: 50rpx 20rpx ;
		border-bottom: solid 1px #eee;
		.date {
			padding-left: 10rpx;
			.uni-input {
				color: rgb(150, 150, 150)
			}
		}
		.time {
			padding-left: 40rpx;
			.uni-input {
				color: rgb(150, 150, 150)
			}
		}
	}
	.input-item{
		padding-left: 40rpx;
		font-size: 20rpx;
	}
	.lineChat {
		width: 100%;
		margin-top: 20rpx;
	}
	.button {
		background: #c8d6e5;
		border-radius: 8px;
		margin-top: 10rpx;
	}
</style>
