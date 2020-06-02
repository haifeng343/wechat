<template>
	<view>
		<view class="close" @click="getBack">
			<image src="../../static/img/close.png" class="close-img" mode="widthFix"></image>
		</view>

		<view class="pc">
			<image src="../../static/img/pc1.png" class="pc1" mode="widthFix"></image>
			<image src="../../static/img/pc_suo.png" v-if="cap2==false" class="pc_suo" mode="widthFix"></image>
			<view class="txt1">Mac微信已登录</view>
			<view class="txt2">手机通知已关闭</view>
		</view>
		<view class="iphone">
			<image src="../../static/img/iPhone.png" v-if="cap1 == false" class="iphone-img" mode="widthFix"></image>
			<image src="../../static/img/jing1.png" v-if="cap1 == false" class="jing1" mode="widthFix"></image>
		</view>

		<view class="list">
			<view class="item" v-for="(item,index) in list" :key="item.id" @click="bindChange(item.id)">
				<view :class="{'item-content':list.length>0,'active':item.flag==true}">
					<image :src="item.flag==true?item.img:item.imgs" class="item-img" mode="widthFix"></image>
				</view>
				<view class="txt">{{item.name}}</view>
			</view>
		</view>
		<text class="exit" @click="exit">退出 Mac 微信</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
					id: 1,
					name: '手机静音',
					img: '../../static/img/jing.png',
					imgs: '../../static/img/jing1.png',
					flag: true,
				}, {
					id: 2,
					name: '锁定',
					img: '../../static/img/suo.png',
					imgs: '../../static/img/suo1.png',
					flag: false
				}, {
					id: 3,
					name: '传文件',
					img: '../../static/img/wenjian.png',
					imgs: '../../static/img/wenjian1.png',
					flag: false
				}],
				cap1: false,
				cap2: true
			}
		},
		methods: {
			//返回上一页
			getBack() {
				uni.navigateBack({
					delta: 1
				})
			},
			//手机电脑状态改变
			bindChange(e) {
				this.showId = e;
				let tempArr = this.list;
				tempArr.forEach(item => {

					if (item.id == e) {
						item.flag = !item.flag;
					}
				})
				this.list = tempArr;
				if (e == 1) {
					this.cap1 = !this.cap1;
				}
				if (e == 2) {
					this.cap2 = !this.cap2;
				}
			},
			//退出mac
			exit() {
				uni.showModal({
					title: '提示？',
					content: '是否退出 Mac 微信',
					confirmColor: '#3F536E',
					success(res) {
						if (res.confirm) {
							uni.showToast({
								icon: "none",
								title: '退出成功！'
							})
						}
					}
				})
			}
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #fff;

		.close {
			width: 40rpx;
			height: 40rpx;
			margin-left: 4%;

			.close-img {
				width: 100%;
				height: 100%;
			}
		}

		.pc {
			width: 300rpx;
			height: 300rpx;
			position: relative;
			left: 0;
			top: 150rpx;
			right: 0;
			bottom: 0;
			margin: auto;
			display: flex;
			flex-direction: column;
			align-items: center;

			.pc1 {
				width: 180rpx;
				height: auto;
			}

			.pc_suo {
				width: 35rpx;
				height: 35rpx;
				position: absolute;
				left: 47%;
				top: 16%;
			}

			.txt1 {
				font-size: 28rpx;
				color: #333333;
				margin-top: 20rpx;
			}

			.txt2 {
				font-size: 24rpx;
				color: #d1d1d1;
			}
		}

		.iphone {
			width: 100rpx;
			height: 100rpx;
			position: relative;
			left: 90rpx;
			top: -60rpx;
			right: 0;
			bottom: 0;
			margin: auto;

			.iphone-img {
				width: 100rpx;
				height: auto;
				background: #fff;
			}

			.jing1 {
				position: absolute;
				width: 25rpx;
				background: #fff;
				height: 25rpx;
				left: 50%;
				top: 50%;
				transform: translate(-50%, -50%);
			}
		}

		.list {
			width: 80%;
			display: flex;
			justify-content: space-around;
			flex-direction: row;
			margin: 80rpx auto 0;

			.item {
				width: 100rpx;
				height: auto;
				display: flex;
				flex-direction: column;
				align-items: center;
				justify-content: center;

				.item-content {
					width: 100rpx;
					height: 100rpx;
					background-color: #e1e1e1;
					display: flex;
					border-radius: 100%;
					align-items: center;
					justify-content: center;

					.item-img {
						width: 40rpx;
						height: auto;
					}
				}

				.active {
					background-color: #4CD964;
				}

				.txt {
					font-size: 18rpx;
					transform: scale(0.8, 0.8);
					color: #c1c1c1;
					margin-top: 8rpx;
				}
			}
		}

		.exit {
			font-size: 32rpx;
			color: #4CD964;
			padding: 15rpx 46rpx;
			border-radius: 8rpx;
			background: #e1e1e1;
			position: absolute;
			bottom: 60rpx;
			left: 50%;
			transform: translateX(-50%);
		}
	}
</style>
