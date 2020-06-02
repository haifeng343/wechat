<template>
	<view>
		<scroll-view scroll-y="true" class="list">
			<view class="item" v-for="item in chatList" :key="item.id">
				<view class="item1" v-if="item.id%2==1">
					<image :src="chatImg" class="chatImg"></image>
					<view class="chatTxt">
						{{item.text}}
					</view>
				</view>
				<view class="item2" v-else>
					<view class="chatTxt">
						{{item.text}}
					</view>
					<image :src="userImg" class="chatImg"></image>
				</view>
			</view>

		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userImg: '',//我的头像
				chatImg: '',//聊天对象头像
				chatTitle:'',//聊天人
				chatList: [{
					id: 1,
					text: '好的 那你也早点休息',
				}, {
					id: 2,
					text: '嗯嗯',
				}, {
					id: 3,
					text: '那我也休息啦'
				}, {
					id: 5,
					text: '晚安'
				}, {
					id: 6,
					text: '晚安'
				},{
					id:7,
					text:'早上好 小可爱'
				}]
			}
		},
		methods: {

		},
		onLoad(options) {
			let that = this;
			let userImg = uni.getStorageSync('userInfo').img;
			that.userImg = userImg;
			that.chatImg = options.img;
			that.chatTitle = options.name;
		},
		onReady() {
			uni.setNavigationBarTitle({
				title:this.chatTitle
			})
		}
	}
</script>

<style lang="scss" scoped>
	.list {
		width: 100%;
		height: auto;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;

		.item {
			width: 97.5%;
			margin: 20rpx auto;
			display: flex;
			align-items: center;

			.item1 {
				justify-content: flex-start;
				.chatImg {
					margin-right: 20rpx;
				}
				.chatTxt {
					background: #fff;
				}
			}

			.item2 {
				justify-content: flex-end;
				.chatImg {
					margin-left: 20rpx;
				}
				.chatTxt {
					background: #4CD000;
				}
			}
		}
	}

	.item1,
	.item2 {
		width: 100%;
		height: auto;
		display: flex;
	}
	.item1 .chatTxt::before{
		content: "";
		position: absolute;
		left: -22rpx;
		top: 16rpx;
		border:12rpx solid transparent;
		border-right: 12rpx solid #fff;
	}
	
	.item2 .chatTxt::before{
		content: "";
		position: absolute;
		right: -22rpx;
		top: 16rpx;
		border:12rpx solid transparent;
		border-left: 12rpx solid #4CD000;
	}

	.chatImg {
		width: 70rpx;
		height: 70rpx;
		border-radius: 8rpx;
	}

	.chatTxt {
		font-size: 28rpx;
		padding: 10rpx 20rpx;
		max-width: 75%;
		display: flex;
		align-items: center;
		border-radius: 8rpx;
		position: relative;
	}
</style>
