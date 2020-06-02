<template>
	<view>
		<view class="qrCode">
			<view class="qrCode-top">
				<view class="avator">
					<image src="../../static/img/avator.jpeg" class="avator-img" mode=""></image>
				</view>
				<view class="qrCode-right">
					<view class="qrCode-title">
						<view class="">?</view>
						<image src="../../static/img/man.png" class="man" mode=""></image>
					</view>
					<view class="qrCode-text">
						中国大陆
					</view>
				</view>
			</view>
			<view class="qrCode-img">
				<image src="../../static/img/codeImg.png" class="codeImg" mode="widthFix"></image>
			</view>
			<view class="qrCode-txt">
				扫一扫上面的二维码图案，加我微信
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.qrCode {
		width: 90%;
		background-color: #fff;
		display: flex;
		flex-direction: column;
		justify-content: center;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);

		.qrCode-top {
			width: 100%;
			height: auto;
			box-sizing: border-box;
			padding: 20rpx;
			display: flex;
			justify-content: flex-start;
			flex-direction: row;

			.avator {
				width: 110rpx;
				height: 110rpx;
				margin-right: 20rpx;

				.avator-img {
					width: 100%;
					height: 100%;
					border-radius: 8rpx;
				}
			}
		}

		.qrCode-right {
			display: flex;
			flex-direction: column;
			justify-content: space-around;

			.qrCode-title {
				font-size: 30rpx;
				color: #555555;
				display: flex;
				align-items: center;
				justify-content: flex-start;

				.man {
					width: 30rpx;
					height: 30rpx;
				}
			}

			.qrCode-text {
				font-size: 24rpx;
				color: #C0C0C0;
			}

		}
		.qrCode-img{
			width: 80%;
			height: auto;
			display: flex;
			justify-content: center;
			margin: 30rpx auto;
			.codeImg{
				width: 100%;
				margin:  0 auto;
			}
		}
		.qrCode-txt{
			font-size: 24rpx;
			color: #C0C0C0;
			text-align: center;
			padding: 30rpx 0;
		}
	}
</style>
