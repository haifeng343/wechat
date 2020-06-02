<template>
	<view>
		<view class="flex-column">
			<view class="money">
				<image src="../../static/img/money1.png" class="money-img" mode=""></image>
			</view>
			<view class="txt1">
				我的零钱
			</view>
			<view class="txt2">
				¥982392.02
			</view>
			<view class="txt3">
				转入零钱通，给自己加加薪
			</view>
			
			<button type="primary">充值</button>
			<button type="default">提现</button>
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
	page {
		background-color: #fff;

		.flex-column {
			width: 100%;
			height: auto;
			display: flex;
			flex-direction: column;
			justify-content: center;
			text-align: center;
			position: relative;
			.money {
				width: 100%;
				height: auto;
				display: flex;
				justify-content: center;

				.money-img {
					width: 100rpx;
					height: 100rpx;
					margin-top: 200rpx;
				}
			}
			.txt1{
				font-size: 28rpx;
				margin-top: 50rpx;
				color: #191919;
			}
			.txt2{
				font-size: 50rpx;
				color: #333333;
				margin: 20rpx 0;
				font-weight: bold;
			}
			.txt3{
				font-size: 20rpx;
				color: #fd942b;
			}
			button{
				width: 50%;
				height: 80rpx;
				background-color: #05c160;
				display: flex;
				align-items: center;
				justify-content: center;
				border: none;
				margin-top: 500rpx;
				font-size: 32rpx;
			}
			button:last-child{
				background-color: #f2f2f2;
				color: #05c160;
				margin-top: 20rpx;
			}
		}
	}
</style>
