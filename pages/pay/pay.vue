<template>
	<view>
		<view class="pay-top">
			<view class="item">
				<image src="../../static/img/pay1.png" class="item-img" mode=""></image>
				<view class="">
					收付款
				</view>
			</view>
			<view class="item" @click="goWallet">
				<image src="../../static/img/pay2.png" class="item-img" mode=""></image>
				<view class="item-text">
					<view class="">
						钱包
					</view>
					<view class="item-text1">
						¥2000.87
					</view>
				</view>
			</view>
		</view>

		<view class="pay-list" v-for="item in payList" :key="item.name">
			<view class="title">{{item.title}}</view>
			<view class="list-pay">
				<view class="item" v-for="item1 in item.list" :key="item1.name">
					<image :src="item1.img" class="item-img" mode=""></image>
					<view class="">
						{{item1.name}}
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
				payList: [
					{
					title: '腾讯服务',
					list: [{
							name: '信用卡还款',
							img: '../../static/img/pay3.png'
						},
						{
							name: '手机充值',
							img: '../../static/img/pay4.png'
						},
						{
							name: '理财通',
							img: '../../static/img/pay5.png'
						},
						{
							name: '生活缴费',
							img: '../../static/img/pay6.png'
						},
						{
							name: '城市服务',
							img: '../../static/img/pay7.png'
						},
						{
							name: '腾讯公益',
							img: '../../static/img/pay8.png'
						},
						{
							name: '医疗健康',
							img: '../../static/img/pay9.png'
						},
					]
				},{
					title: '限时推广',
					list: [{
							name: '防疫健康码',
							img: '../../static/img/pay10.png'
						},
					]
				},{
					title: '第三方服务',
					list: [{
							name: '火车票机票',
							img: '../../static/img/pay11.png'
						},
						{
							name: '滴滴出行',
							img: '../../static/img/pay12.png'
						},
						{
							name: '京东购物',
							img: '../../static/img/pay13.png'
						},
						{
							name: '美团外卖',
							img: '../../static/img/pay14.png'
						},
						{
							name: '电影演出赛事',
							img: '../../static/img/pay15.png'
						},
						{
							name: '吃喝玩乐',
							img: '../../static/img/pay16.png'
						},
						{
							name: '酒店',
							img: '../../static/img/pay17.png'
						},{
							name: '蘑菇街女装',
							img: '../../static/img/pay18.png'
						},
						{
							name: '唯品会特卖',
							img: '../../static/img/pay19.png'
						},
						{
							name: '转转二手',
							img: '../../static/img/pay20.png'
						},
						{
							name: '贝壳找房',
							img: '../../static/img/pay21.png'
						}
					]
				},
				]
			}
		},
		methods: {
			//钱包
			goWallet(){
				uni.navigateTo({
					url:'../wallet/wallet'
				})
			}
		}
	}
</script>

<style lang="scss">
	.pay-top {
		width: 96%;
		height: 300rpx;
		margin: 20rpx auto 0;
		border-radius: 15rpx;
		background-color: #3bac6a;
		display: flex;
		flex: 1;
		justify-content: space-around;

		.item {
			width: auto;
			height: auto;
			display: flex;
			flex: 1;
			flex-direction: column;
			align-items: center;
			font-size: 32rpx;
			color: #fff;
			position: relative;
			overflow: hidden;

			.item-text {
				display: flex;
				flex-direction: column;
				text-align: center;

				.item-text1 {
					opacity: .6;
					position: absolute;
					left: 50%;
					top: 50%;
					transform: translate(-50%, -50%);
					margin-top: 56rpx;
				}
			}

			.item-img {
				width: 50rpx;
				height: 50rpx;
				margin-bottom: 20rpx;
				margin-top: 70rpx;
			}
		}
	}

	.pay-list {
		width: 96%;
		height: auto;
		background-color: #fff;
		border-radius: 15rpx;
		display: flex;
		flex-direction: column;
		margin: 20rpx auto 0;
		.title {
			font-size: 28rpx;
			color: #7f7f7f;
			padding: 0 4%;
			width: 100%;
			height: 80rpx;
			display: flex;
			align-items: center;
			box-sizing: border-box;
			border-bottom: 1rpx solid #e5e5e5;
		}
		.list-pay{
			width: 100%;
			height: auto;
			display: flex;
			flex-wrap: wrap;
			justify-content: flex-start;
			box-sizing: border-box;
			border: 1rpx solid #FFFFFF;
			.item {
				width: 33.33%;
				height: 220rpx;
				border-right: 1rpx solid #e5e5e5;
				border-bottom: 1rpx solid #e5e5e5;
				box-sizing: border-box;
				display: flex;
				flex-direction: column;
				align-items: center;
				justify-content: center;
				font-size: 28rpx;
				color: #333333;
			
				.item-img {
					width: 50rpx;
					height: 50rpx;
					margin-bottom: 20rpx;
				}
			}
			.item:nth-child(3n){
				border-right: none;
			}
			.item:nth-child(n+10){
				border-bottom: none;
			}
			.item:last-child{
				border-bottom:none;
			}
			.item:nth-child(-n+3) {
				
			}
		}
	}
	.pay-list{
		margin-bottom: 30rpx;
	}
</style>
