<template>
	<view class="">
		<!-- 顶部 -->
		<view class="people-list" id="top">
			<view class="">
				<view class="people-item" v-for="(item,index) in listTop" :key="item.code">
					<view class="people-item-left">
						<image :src="item.img" class="people-avator" mode=""></image>
					</view>
					<view class="people-item-right">
						<view class="people-item-right-top">
							<view class="people-item-right-title">{{item.name}}</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 内容 -->
		<view class="people-list">
			<view class="" v-for="(item,index) in listd" :key="item.id">
				<view class="item-name" :id="'q'+item.name" :name="'q'+item.name">{{item.name}}</view>
				<view class="people-item" v-for="item1 in item.spits" :key="item1.id" @click="goPeople">
					<view class="people-item-left">
						<image :src="item1.img" class="people-avator" mode=""></image>
					</view>
					<view class="people-item-right">
						<view class="people-item-right-top">
							<view class="people-item-right-title">{{item1.name}}</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- <view class="" @click="goTop">
			top
		</view> -->
		<view class="rightList">
			<view class="item" v-for="item in AZList" :key="item">
				<a href="javascript:void(0)" @click="toTop('#q'+item)">{{item}}</a>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'index',
		data() {
			return {
				AZList: [], //A-Z
				listd: [{
					name: 'A',
					spits: [{
						id: 1,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}, {
						id: 2,
						name: '魏大勋',
						img: '../../static/img/avator12.jpeg',
						text: '今晚看球赛吗？',
						time: "11:32",
						shike: '中午',
					}, {
						id: 3,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					}, {
						id: 4,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					}]
				}, {
					name: 'B',
					spits: [{
						id: 5,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}, {
						id: 6,
						name: '魏大勋',
						img: '../../static/img/avator12.jpeg',
						text: '今晚看球赛吗？',
						time: "11:32",
						shike: '中午',
					}, {
						id: 7,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					}, {
						id: 8,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					}]
				}, {
					name: 'C',
					spits: [{
						id: 9,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}, {
						id: 10,
						name: '魏大勋',
						img: '../../static/img/avator12.jpeg',
						text: '今晚看球赛吗？',
						time: "11:32",
						shike: '中午',
					}, {
						id: 11,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					}]
				}, {
					name: 'D',
					spits: [{
						id: 12,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}, {
						id: 13,
						name: '魏大勋',
						img: '../../static/img/avator12.jpeg',
						text: '今晚看球赛吗？',
						time: "11:32",
						shike: '中午',
					}, {
						id: 14,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					},{
						id: 15,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}, {
						id: 16,
						name: '魏大勋',
						img: '../../static/img/avator12.jpeg',
						text: '今晚看球赛吗？',
						time: "11:32",
						shike: '中午',
					}, {
						id: 17,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					},{
						id: 18,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}, {
						id: 19,
						name: '魏大勋',
						img: '../../static/img/avator12.jpeg',
						text: '今晚看球赛吗？',
						time: "11:32",
						shike: '中午',
					}, {
						id: 20,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					},{
						id: 21,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}, {
						id: 22,
						name: '魏大勋',
						img: '../../static/img/avator12.jpeg',
						text: '今晚看球赛吗？',
						time: "11:32",
						shike: '中午',
					}, {
						id: 23,
						name: '范冰冰',
						img: '../../static/img/avator11.jpeg',
						text: '等你吃饭噢',
						time: "9:35",
						shike: '晚上',
					},{
						id: 24,
						name: '冯先生',
						img: '../../static/img/avator.jpeg',
						text: '嗯嗯 好的那我知道了',
						time: "10:20",
						shike: '上午',
						imgd: '../../static/img/mute.png'
					}]
				}],
				listTop: [{
					code: 1,
					name: '新的朋友',
					img: '../../static/img/tong1.png',
				}, {
					code: 2,
					name: '群聊',
					img: '../../static/img/tong2.png',
				}, {
					code: 3,
					name: '标签',
					img: '../../static/img/tong3.png',
				}, {
					code: 4,
					name: '公众号',
					img: '../../static/img/tong4.png',
				}, ]
			}
		},
		onLoad() {
			//调用赋值
			this.getEN();
			let arr = this.AZList;
			arr.unshift('↑', '☆');
			this.AZList = arr;


		},
		methods: {
			navto() {
				uni.navigateTo({
					url: '../mac/mac'
				})
			},
			//排序a-z
			getEN() {
				let arr = [];
				for (var i = 65; i < 91; i++) {
					arr.push(String.fromCharCode(i));
				}
				this.AZList = arr;
			},
			//回到顶部
			goTop() {
				uni.pageScrollTo({
					scrollTop: 0,
					duration: 500
				})
			},
			toTop(e){
				if(e=='#q↑' || e== '#q☆'){
					this.goTop();
				}else{
					let arr = this.listd;
					arr.forEach(item=>{
						if(('#q'+item.name) == e){
							document.querySelector(e).scrollIntoView(true);
						}else{
							
						}
					})
					console.log(e);
				}
				// let ancor = this.$el.querySelector(e);
				// document.body.scrollTop = ancor.scrollTop;
				
				
			},
			goPeople(){
				uni.navigateTo({
					url:'../pyq/pyq'
				})
			}
		}
	}
</script>

<style lang="scss">
	.people-list {
		width: 100%;
		height: auto;
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		border-top: 1rpx solid #e9e9e9;
		border-bottom: 1rpx solid #e9e9e9;

		.item-name {
			height: 50rpx;
			margin-left: 4%;
			display: flex;
			align-items: center;
			font-size: 20rpx;
			color: #555555;
		}

		.people-item {
			width: 100%;
			height: 90rpx;
			padding: 20rpx 0;
			background-color: #fff;
			display: flex;
			align-items: center;

			.people-item-left {
				width: auto;
				height: auto;
				display: flex;
				box-sizing: border-box;
				padding-left: 4%;
				align-items: center;

				.people-avator {
					width: 90rpx;
					height: 90rpx;
					border-radius: 8rpx;
					margin-right: 20rpx;
				}
			}

			.people-item-right {
				display: flex;
				flex: 1;
				height: 120rpx;
				justify-content: center;
				align-items: center;
				flex-direction: column;
				box-sizing: border-box;
				border-bottom: 1rpx solid #e9e9e9;

				.people-item-right-top {
					width: 100%;
					display: flex;
					justify-content: space-between;

					.people-item-right-title {
						font-size: 28rpx;
						font-weight: 400 !important;
						color: #333333;
					}
				}
			}
		}

		.people-item:last-child .people-item-right {
			border: none;
		}
	}

	.rightList {
		height: auto;
		width: 60rpx;
		position: fixed;
		right: 0;
		top: 0;
		bottom: 0;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		z-index: 1;

		.item {
			width: 100%;
			height: 36rpx;
			display: flex;
			align-items: center;
			justify-content: center;
			font-size: 22rpx;
			color: #555555;
		}
	}
</style>
