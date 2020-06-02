<template>
	<view>
		<view class="top">
			<view class="top-img">
				<image src="../../static/img/linqian.png" class="topImg" mode=""></image>
			</view>
			<view class="top-text">
				零钱通
			</view>
		</view>
		<view class="linqian-container">
			<view class="title">
				<view class="t1">
					账户余额
				</view>
				<view class="t2">
						¥
						<view class="money">
							397923.29
						</view>
				</view>
			</view>
			<view class="content">
				<view class="item">
					<view class="t1">
						7日年化收益率
					</view>
					<view class="t2">
						1.7364%
					</view>
					<text class="t3">
						富国富钱包
					</text>
				</view>
				
					<view class="item">
						<view class="t1">
							累计收益
						</view>
						<view class="t2">
							¥267283.23
						</view>
						<text class="t3">
							昨日¥89.35
						</text>
					</view>
			</view>
			<view class="btn btns">
				转入
			</view>
			<view class="btn">
				转出
			</view>
			<view class="bottom">
				<view class="middle">
					<image src="../../static/img/card.png" class="card" mode=""></image>
					工资卡自动转入
				</view>
				<image src="../../static/img/right.png" class="right" mode=""></image>
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
	page{
		background-color: #f3b802;
		.top{
			width: 100%;
			height: auto;
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			margin-top: 60rpx;
			.top-img{
				width: 70rpx;
				height: 70rpx;
				border-radius: 100%;
				display: flex;
				align-items: center;
				background-color: #FFFFFF;
				justify-content: center;
				.topImg{
					width: 55rpx;
					height: 55rpx;
				}
			}
			.top-text{
				font-size: 26rpx;
				color: #FFFFFF;
				margin: 20rpx auto;
			}
		}
		.linqian-container{
			width: 95%;
			margin: 20rpx auto;
			height: auto;
			border-radius: 16rpx;
			background-color: #FFFFFF;
			.title{
				width: 100%;
				text-align: center;
				display: flex;
				align-items: center;
				justify-content: center;
				flex-direction: column;
				padding-top: 40rpx;
				.t1{
					font-size: 20rpx;
				}
				.t2{
					display: flex;
					justify-content: flex-start;
					font-size: 38rpx;
					font-weight: bold;
					align-items: center;
					.money{
						font-size: 60rpx;
						margin-left: 6rpx;
					}
				}
			}
			.bottom{
				width: 93%;
				height: 100rpx;
				padding: 0 3.5%;
				border-top: 20rpx solid #f9f9f9;
				display: flex;
				justify-content: space-between;
				flex-direction: row;
				align-items: center;
				margin-top: 80rpx;
				.card{
					width: 54rpx;
					height: 54rpx;
					margin-right: 20rpx;
				}
				.middle{
					display: flex;
					align-items: center;
					font-size: 28rpx;
					font-weight: 500;
					color: #333333;
				}
				.right{
					width: 18rpx;
					height: 22rpx;
				}
			}
			.content{
				width: 80%;
				height: auto;
				display: flex;
				margin: 80rpx auto;
				justify-content: space-between;
				flex-direction: row;
				.item{
					width: 50%;
					box-sizing: border-box;
					text-align: center;
					font-size: 32rpx;
					.t1{
						font-size: 26rpx;
						color: #C0C0C0;
					}
					.t2{
						margin: 10rpx 0;
					}
					.t3{
						padding: 5rpx 10rpx;
						background-color: #f9f9f9;
						border-radius: 25rpx;
						font-size: 20rpx;
					}
				}
			}
			.btn{
				width: 360rpx;
				height: 80rpx;
				border-radius: 8rpx;
				display: flex;
				justify-content: center;
				align-items: center;
				margin: 20rpx auto 0;
				background-color: #f9f9f9;
				color: #F0AD4E;
				font-size: 28rpx;
			}
			.btns{
				background-color: #F0AD4E;
				color: #fff;
			}
		}
	}
	.content .item:first-child{
		border-right: 2rpx solid #eee;
	}
</style>
