<template>
	<view>
		<view class="flex-column">
			<view class="money">
				<image src="../../static/img/w_kabao.png" class="money-img" mode=""></image>
			</view>
			<view class="txt1">
				亲属卡
			</view>
			<view class="txt2">
				送父母子女亲属卡
			</view>
			<view class="txt2">
				对方消费由我买单
			</view>
			<view class="txt2">
				让支付更简单
			</view>
			<button type="default">赠送</button>
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
					margin-bottom: 40rpx;
				}
			}
			.txt1{
				font-size: 42rpx;
				font-weight: 400;
				margin: 20rpx 0;
			}
			.txt2{
				font-size: 28rpx;
				color: #333333;
				margin: 15rpx 0;
			}
			button{
				width: 50%;
				height: 80rpx;
				color: #FFFFFF;
				background-color: #fa9e3b;
				display: flex;
				align-items: center;
				justify-content: center;
				border: none;
				margin-top: 40rpx;
				font-size: 32rpx;
			}
		}
	}
</style>
