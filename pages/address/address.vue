<template>
	<view>
		<view class="list">
			<view class="item" @longtap="edit">
				<view class="item-top">
					冯，15123754227
				</view>
				<view class="item-bottom">
					黑龙江省 哈尔滨市 南岗区 新田
				</view>
			</view>
			<view class="item">
				<view class="item-top">
					冯，15123754227
				</view>
				<view class="item-bottom">
					黑龙江省 哈尔滨市 南岗区 新田
				</view>
			</view>
			<view class="item">
				<view class="item-top">
					冯，15123754227
				</view>
				<view class="item-bottom">
					黑龙江省 哈尔滨市 南岗区 新田
				</view>
			</view>
			<view class="item">
				<view class="item-top">
					冯，15123754227
				</view>
				<view class="item-bottom">
					黑龙江省 哈尔滨市 南岗区 新田
				</view>
			</view>
			<view class="item">
				<view class="item-top">
					冯，15123754227
				</view>
				<view class="item-bottom">
					黑龙江省 哈尔滨市 南岗区 新田
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
			edit(){
				uni.showActionSheet({
					itemList:['复制','编辑','删除'],
					success(res) {
						if(res.tapIndex==0){
							uni.showToast({
								title:'复制成功!',
								icon:"none"
							})
						}
						if(res.tapIndex==1){
							uni.showToast({
								title:'编辑成功!',
								icon:"none"
							})
						}
						if(res.tapIndex==2){
							uni.showToast({
								title:'删除成功!',
								icon:"none"
							})
						}
					}
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
		background-color: #fff;
		flex-direction: column;

		.item {
			width: 97%;
			min-height: 90rpx;
			padding: 10rpx 0;
			display: flex;
			flex-direction: column;
			justify-content: space-around;
			margin-left: 3%;
			border-bottom: 1rpx solid #F1F1F1;
			.item-top{
				font-size: 28rpx;
				color: #333333;
			}
			.item-bottom{
				font-size: 24rpx;
				color: #808080;
			}
			
		}
	}
</style>
