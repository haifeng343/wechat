<template>
	<view>
		<view class="container">
			<view class="content">
				<view class="my-top">
					<view class="paishe">
						<image src="../../static/img/paishe.png" class="paishe_img" mode=""></image>
					</view>
					<view class="userInfo">
						<view class="userInfo-left">
							<view class="userInfo-avator">
								<image src="../../static/img/avator.jpeg" class="avator" mode=""></image>
							</view>
							<view class="userInfo-msg">
								<view class="userInfo-name">
									?
								</view>
								<view class="userInfo-code">
									微信号:F15123754227
								</view>
							</view>
						</view>
						<view class="userInfo-right" @click="goUser">
							<image src="../../static/img/w_code.png" class="code" mode="widthFix"></image>
							<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item" @click="pay">
				<view class="item-left">
					<image src="../../static/img/w_pay.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">支付</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/w_shoucang.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">收藏</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/w_photo.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">相册</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/w_kabao.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">卡包</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/w_biaoqing.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">表情</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/w_set.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">设置</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'mine',
		data() {
			return {

			}
		},
		methods: {
			//我的信息
			goUser(){
				uni.navigateTo({
					url:"../userInfo/userInfo"
				})
			},
			//支付
			pay(){
				uni.navigateTo({
					url:'../pay/pay'
				})
			},
		}
	}
</script>

<style lang="scss">
	.my-top {
		width: 100%;
		height: auto;
		display: flex;
		flex-direction: column;
		background-color: #fff;

		.paishe {
			width: 100%;
			height: 100rpx;
			display: flex;
			align-items: center;
			justify-content: flex-end;

			.paishe_img {
				width: 40rpx;
				height: 32rpx;
			}
		}

		.userInfo {
			width: 100%;
			height: 200rpx;
			display: flex;
			justify-content: space-between;

			.userInfo-left {
				width: 70%;
				height: auto;
				overflow: hidden;
				display: flex;
				justify-content: flex-start;

				.userInfo-avator {
					width: 130rpx;
					height: 130rpx;
					overflow: hidden;
					margin-right: 20rpx;

					.avator {
						width: 100%;
						height: 100%;
						border-radius: 8rpx;
					}
				}

				.userInfo-msg {
					height: 120rpx;
					display: flex;
					flex-direction: column;
					justify-content: space-between;

					.userInfo-name {
						font-size: 32rpx;
						color: #000000;
						font-weight: bold;
					}

					.userInfo-code {
						color: #8F8F94;
						font-size: 28rpx;
						font-weight: 400;
					}
				}
			}

			.userInfo-right {
				width: auto;
				height: 120rpx;
				display: flex;
				align-items: flex-end;

				.code {
					width: 40rpx;
					height: 40rpx;
					margin-right: 20rpx;
				}

				.right {
					width: 30rpx;
					height: 16rpx;
					margin-bottom: 6rpx;
					display: flex;
					align-items: center;
				}
			}
		}
	}

	.list {
		width: 100%;
		height: auto;
		display: flex;
		margin-top: 20rpx;
		flex-direction: column;

		.item {
			width: 100%;
			height: 110rpx;
			background-color: #fff;
			box-sizing: border-box;
			display: flex;
			align-items: center;
			justify-content: space-between;
			font-size: 32rpx;
			color: #000;

			.item-left {
				width: auto;
				height: auto;
				margin-left: 4%;
				margin-right: 20rpx;
				display: flex;
				align-items: center;
				.item-left-img {
					width: 35rpx;
					height: 35rpx;
				}
			}

			.item-right {
				height: 110rpx;
				display: flex;
				flex: 1;
				align-items: center;
				justify-content: space-between;
				box-sizing: border-box;
				border-bottom: 1rpx solid #F5F5F5;

				.right {
					width: 30rpx;
					height: 16rpx;
					margin-right: 4%;
				}
			}

		}
		.item:last-child{
			.item-right{
				border: none;
			}
		}
	}
</style>
