<template>
	<view class="">
		<view class="mac" @click="navto">
			<image src="../../static/img/pc.png" class="pc" mode=""></image>
			<view class="">
				Mac微信已登录，手机通知已关闭
			</view>
		</view>
		<view class="people-list">
			<view class="people-item" @click="sendTo(item)" v-for="(item,index) in list" :key="item.id">
				<view class="people-item-left">
					<image :src="item.img" class="people-avator" mode=""></image>
				</view>
				<view class="people-item-right">
					<view class="people-item-right-top">
						<view class="people-item-right-title">{{item.name}}</view>
						<view class="people-item-right-time">{{item.shike}}{{item.time}}</view>
					</view>
					<view class="people-item-right-bottom">
						<view class="people-item-right-text">{{item.text}}</view>
						<image v-if="item.imgd" :src="item.imgd" class="people-mote" mode="widthFix"></image>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'index',
		data() {
			return {
				list: [{
					id: 1,
					name: '冯先生',
					img: '../../static/img/avator.jpeg',
					text: '嗯嗯 好的那我知道了',
					time: "10:20",
					shike: '上午',
					imgd: '../../static/img/mute.png'
				}, {
					id: 2,
					name: '张小姐',
					img: '../../static/img/avator1.jpeg',
					text: '那你早点回去吧',
					time: "3:22",
					shike: '下午',
				}, {
					id: 3,
					name: '罗女士',
					img: '../../static/img/avator2.jpeg',
					text: '[动作表情][动作表情]',
					time: "3:32",
					shike: '下午',
				}, {
					id: 4,
					name: '陈小姐',
					img: '../../static/img/avator3.jpeg',
					text: '[动作表情] 赶紧上线',
					time: "1:26",
					shike: '下午',
				}, {
					id: 5,
					name: '蔡先生',
					img: '../../static/img/avator4.jpeg',
					text: '[动作表情][动作表情][动作表情][动作表情][动作表情]',
					time: "8:56",
					shike: '晚上',
				}, {
					id: 6,
					name: '张先生',
					img: '../../static/img/avator5.jpeg',
					text: '好的呢',
					time: "10:20",
					shike: '晚上',
				}, {
					id: 7,
					name: '马云',
					img: '../../static/img/avator6.jpeg',
					text: '那我马上处理',
					time: "7:20",
					shike: '上午',
				}, {
					id: 8,
					name: '郭富城',
					img: '../../static/img/avator7.jpeg',
					text: '马上打钱',
					time: "9:30",
					shike: '上午',
				}, {
					id: 9,
					name: '黎明',
					img: '../../static/img/avator8.jpeg',
					text: '什么时候来演唱会？',
					time: "12:20",
					shike: '中午',
				}, {
					id: 10,
					name: '迪丽热巴',
					img: '../../static/img/avator9.jpeg',
					text: '还不赶紧来吃饭？干嘛呢',
					time: "12:20",
					shike: '中午',
				}, {
					id: 11,
					name: '杨幂',
					img: '../../static/img/avator10.jpeg',
					text: '今晚有时间一起吃饭？',
					time: "12:30",
					shike: '中午',
				}, {
					id: 12,
					name: '范冰冰',
					img: '../../static/img/avator11.jpeg',
					text: '等你吃饭噢',
					time: "9:35",
					shike: '晚上',
				},{
					id: 13,
					name: '魏大勋',
					img: '../../static/img/avator12.jpeg',
					text: '今晚看球赛吗？',
					time: "11:32",
					shike: '中午',
				}]
			}
		},
		onLoad() {

		},
		methods: {
			navto(){
				uni.navigateTo({
					url:'../mac/mac'
				})
			},
			sendTo(e){
				uni.navigateTo({
					url:'../chat/chat?id='+e.id+'&name='+e.name+'&img='+e.img
				})
			}
		}
	}
</script>

<style lang="scss">
	.mac {
		width: 100%;
		height: 80rpx;
		display: flex;
		align-items: center;
		font-size: 26rpx;
		color: #333333;
		background-color: #f7f7f7;

		.pc {
			width: 36rpx;
			height: 38rpx;
			margin: 0 6%;
		}
	}
	
	.people-list{
		width: 100%;
		height: auto;
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		border-top: 1rpx solid #e9e9e9;
		border-bottom: 1rpx solid #e9e9e9;
		.people-item{
			width: 100%;
			height: 100rpx;
			padding: 20rpx 0;
			background-color: #fff;
			display: flex;
			align-items: center;
			.people-item-left{
				width: auto;
				height: auto;
				display: flex;
				box-sizing: border-box;
				padding-left: 4%;
				align-items: center;
				.people-avator{
					width: 90rpx;
					height: 90rpx;
					border-radius: 8rpx;
					margin-right: 20rpx;
				}
			}
			.people-item-right{
				display: flex;
				flex: 1;
				height: 140rpx;
				justify-content: center;
				align-items: center;
				flex-direction: column;
				box-sizing: border-box;
				border-bottom: 1rpx solid #e9e9e9;
				.people-item-right-top{
					width: 100%;
					display: flex;
					justify-content: space-between;
					.people-item-right-title{
						font-size: 32rpx;
						font-weight: 500;
						color: #333333;
					}
					.people-item-right-time{
						font-size: 24rpx;
						color: #999999;
						margin-right: 4%;
					}
				}
				.people-item-right-bottom{
					display: flex;
					width: 100%;
					justify-content: space-between;
					align-items: center;
					font-size: 22rpx;
					color: #908f8f;
					.people-item-right-text{
						width: 87%;
						overflow: hidden;
						text-overflow: ellipsis;
						white-space: nowrap;
					}
					.people-mote{
						width: 20rpx;
						height: 26rpx;
						margin-right: 4%;
					}
				}
			}
		}
		
		.people-item:last-child .people-item-right{
			border: none;
		}
	}
</style>
