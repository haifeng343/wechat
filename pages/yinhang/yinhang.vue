<template>
	<view>
		<view class="list">
			<view class="item" v-for="item in list" :key="item.number">
				<view class="item-top">
					<view class="item-img">
						<image :src="item.img" class="item-bankImg" mode=""></image>
					</view>
					<view class="flex-column">
						<view class="item-top-title">
							{{item.name}}
						</view>
						<view class="item-top-txt">
							{{item.text}}
						</view>
					</view>
				</view>
				<view class="item-bottom">
					{{item.number}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					{
						name:'浙商农信',
						text:'储蓄卡',
						img:'../../static/img/bank2.png',
						number:'..............9023'
					},{
						name:'中国工商',
						text:'储蓄卡',
						img:'../../static/img/bank4.png',
						number:'..............3452'
					},{
						name:'招商银行',
						text:'储蓄卡',
						img:'../../static/img/bank1.png',
						number:'..............5695'
					},{
						name:'民生银行',
						text:'储蓄卡',
						img:'../../static/img/bank3.png',
						number:'..............6126'
					},
				]
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
		flex-direction: column;
		.item{
			width: 100%;
			height: 250rpx;
			border-radius: 8rpx;
			box-sizing: border-box;
			padding: 40rpx 30rpx;
			color: #fff;
			background-color: #3F536E;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			margin-top: 20rpx;
			.item-top{
				width: 100%;
				height: auto;
				display: flex;
				align-items: center;
				justify-content: flex-start;
				.item-img{
					width: 80rpx;
					height: 80rpx;
					background-color: #fff;
					border-radius: 100%;
					margin-right: 30rpx;
					.item-bankImg{
						width: 60rpx;
						height: 60rpx;
						border: 10rpx solid #f1f1f1;
						border-radius: 100%;
					}
				}
				.item-top-title{
					font-size: 30rpx;
				}
				.item-top-txt{
					font-size: 24rpx;
				}
			}
			.item-bottom{
				font-size: 40rpx;
				letter-spacing: .5em;
			}
		}
	}
	.item:nth-child(2n+1){
		background-color: #DD524D;
	}
</style>
