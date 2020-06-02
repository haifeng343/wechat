<template>
	<view>
		<view class="list">
			<!-- <view class="item">
				<view class="item-left">
					<image src="../../static/img/wallet0.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">账单</view>
					<view class="item-text1">
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
			</view> -->
			<view class="item" @click="goMoney">
				<view class="item-left">
					<image src="../../static/img/wallet1.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">零钱</view>
					<view class="item-text1">
						<view class="">
							¥1723.23
						</view>
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
			</view>
			<view class="item" @click="goLinqian">
				<view class="item-left">
					<image src="../../static/img/wallet2.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">零钱通<text class="shouyi">收益率7.28%</text></view>
					<view class="item-text1">
						<view class="">
							¥82263.90
						</view>
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
			</view>
			<view class="item" @click="goYinhang">
				<view class="item-left">
					<image src="../../static/img/wallet3.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">银行卡</view>
					<view class="item-text1">
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item" @click="goParent">
				<view class="item-left">
					<image src="../../static/img/wallet4.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">亲属卡</view>
					<view class="item-text1">
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
			</view>
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/wallet5.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">银行储蓄</view>
					<view class="item-text1">
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/wallet6.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">安全保障</view>
					<view class="item-text1">
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
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
			//零钱
			goMoney(){
				uni.navigateTo({
					url:'../money/money'
				})
			},
			//亲属卡
			goParent(){
				uni.navigateTo({
					url:'../parent/parent'
				})
			},
			//银行卡
			goYinhang(){
				uni.navigateTo({
					url:'../yinhang/yinhang'
				})
			},
			//零钱通
			goLinqian(){
				uni.navigateTo({
					url:'../linqian/linqian'
				})
			}
		}
	}
</script>

<style lang="scss">
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
					width: 45rpx;
					height: 45rpx;
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

				.item-text {
					color: #333333;
					.shouyi{
						color: #dcae7d;
						background-color: #ffebcd;
						font-size: 20rpx;
						padding: 2rpx 10rpx;
						border-radius: 4rpx;
						margin-left: 10rpx;
					}
				}

				.item-text1 {
					display: flex;
					justify-content: flex-end;
					align-items: center;
					color: #000;
					margin-right: 4%;

					.right {
						width: 30rpx;
						height: 16rpx;
						margin-left: 20rpx;
					}
				}
			}

		}

		.item:last-child {
			.item-right {
				border: none;
			}
		}
	}

	.list:first-child {
		margin-top: 0;
	}
</style>
