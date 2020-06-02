<template>
	<view>
		<view class="list">
			<view class="item" @click="avatorChange">
				<view class="item-left">
					头像
				</view>
				<view class="item-right">
					<view class="avator" @click.stop="goAvator">
						<image :src="userInfo.img" class="avator-img" mode=""></image>
					</view>
					<image src="../../static/img/right.png" class="right" mode=""></image>
				</view>
			</view>
			<view class="item" @click="editName">
				<view class="item-left">
					昵称
				</view>
				<view class="item-right">
					<view class="">
						{{userInfo.name}}
					</view>
					<image src="../../static/img/right.png" class="right" mode=""></image>
				</view>
			</view>
			<view class="item">
				<view class="item-left">
					微信号
				</view>
				<view class="item-right">
					{{userInfo.code}}
				</view>
			</view>
			<view class="item" @click="goQrCode">
				<view class="item-left">
					二维码名片
				</view>
				<view class="item-right">
					<image src="../../static/img/w_code.png" class="code" mode=""></image>
					<image src="../../static/img/right.png" class="right" mode=""></image>
				</view>
			</view>
			<view class="item" @click="goMore">
				<view class="item-left">
					更多
				</view>
				<view class="item-right">
					<image src="../../static/img/right.png" class="right" mode=""></image>
				</view>
			</view>
		</view>
		<view class="list">
			<view class="item" @click="goAddress">
				<view class="item-left">
					我的地址
				</view>
				<view class="item-right">
					<image src="../../static/img/right.png" class="right" mode=""></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		 name:"userInfo",
		data() {
			return {
				userInfo:{},
			}
		},
		onShow() {
			this.userInfo = uni.getStorageSync('userInfo');
		},
		mounted() {
			let userInfo1 = {
				name:'?',
				img:'../../static/img/avator.jpeg',
				code:'F15123754227',
				sex:'男',
				area:'中国大陆',
				text:'山高路远总有人为你而来'
			}
			uni.setStorageSync("userInfo",userInfo1);
			this.userInfo = uni.getStorageSync('userInfo');
		},
		methods: {
			goAvator(){
				uni.navigateTo({
					url:'../avator/avator'
				})
			},
			//调取系统相册
			avatorChange(){
				uni.chooseImage({
					count:1,
					sizeType:"original",
					success(res) {
						console.log(res);
						uni.previewImage({
							 // 对选中的图片进行预览
							urls: res.tempFilePaths,
						})
					}
				})
			},
			//修改昵称
			editName(){
				uni.navigateTo({
					url:'../editName/editName'
				})
			},
			//二维码名片
			goQrCode(){
				uni.navigateTo({
					url:'../qrCode/qrCode'
				})
			},
			//更多
			goMore(){
					uni.navigateTo({
						url:'../editMore/editMore'
					})
			},
			//地址
			goAddress(){
				uni.navigateTo({
					url:'../address/address'
				})
			}
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
				font-size: 30rpx;
				color: #808080;
				display: flex;
				flex-direction: row;
				align-items: center;
				box-sizing: border-box;
				padding-right: 3%;
				.avator{
					width: 90rpx;
					height: 90rpx;
					padding: 10rpx 0;
					.avator-img{
						width: 100%;
						height: 100%;
						border-radius: 8rpx;
					}
				}
				.code{
					width: 30rpx;
					height: 30rpx;
				}
				.right{
					width: 25rpx;
					height: 25rpx;
					margin-left: 20rpx;
				}
			}
		}
	}
	.list:last-child{
		margin-top: 20rpx;
	}
	.item:last-child{
		border: none;
	}
</style>
