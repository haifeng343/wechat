<template>
	<view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find1.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">朋友圈</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find2.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">视频号</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
		
			<view class="list">
				<view class="item">
					<view class="item-left">
						<image src="../../static/img/find3.png" class="item-left-img" mode=""></image>
					</view>
					<view class="item-right">
						<view class="item-text">扫一扫</view>
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
				<view class="item">
					<view class="item-left">
						<image src="../../static/img/find4.png" class="item-left-img" mode=""></image>
					</view>
					<view class="item-right">
						<view class="item-text">摇一摇</view>
						<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
					</view>
				</view>
			</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find5.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">看一看</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find6.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">搜一搜</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find7.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">附近的人</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find8.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">购物</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find9.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">游戏</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item">
				<view class="item-left">
					<image src="../../static/img/find10.png" class="item-left-img" mode=""></image>
				</view>
				<view class="item-right">
					<view class="item-text">小程序</view>
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
	.list:first-child{
		margin-top: 0;
	}
</style>
