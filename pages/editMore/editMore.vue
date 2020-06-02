<template>
	<view>
		<view class="list">
			<view class="item" @click="avatorChange">
				<view class="item-left">
					性别
				</view>
				<view class="item-right">
					<view class="item-right-text">
						男
					</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
			<view class="item" @click="avatorChange">
				<view class="item-left">
					地区
				</view>
				<view class="item-right">
					<view class="item-right-text">
						中国大陆
					</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
				</view>
			</view>
			<view class="item" @click="avatorChange">
				<view class="item-left">
					个性签名
				</view>
				<view class="item-right">
					<view class="item-right-text">
						山高路远总有人为你而来
					</view>
					<image src="../../static/img/right.png" class="right" mode="widthFix"></image>
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

		}
	}
</script>

<style lang="scss">
	.list{
		width: 100%;
		height: auto;
		display: flex;
		background-color: #fff;
		flex-direction: column;
		.item{
			width: 97%;
			min-height: 90rpx;
			display: flex;
			align-items: center;
			justify-content: space-between;
			margin-left: 3%;
			border-bottom: 1rpx solid #F1F1F1;
			.item-left{
				font-size: 32rpx;
				color: #333333;
			}
			.item-right{
				width: 70%;
				font-size: 30rpx;
				color: #808080;
				display: flex;
				flex-direction: row;
				align-items: center;
				text-align: right;
				justify-content: flex-end;
				justify-content: flex-end;
				box-sizing: border-box;
				padding-right: 3%;
				.item-right-text{
					width: 70%;
					overflow: hidden;
					text-overflow: ellipsis;
					white-space: nowrap;
				}
				.right{
					width: 25rpx;
					margin-left: 20rpx;
				}
			}
		}
	}
	.item:last-child{
		border: none;
	}
</style>
