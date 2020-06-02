<template>
	<view>
		<view class="edit">
			<view class="flex-end">
				<button type="primary" size="mini" class="btn" :disabled="IsDisabled" @click="send">保存</button>
			</view>
			<view class="flex-column">
				<input type="text" :class="{'name':true,'borderbottom':isFocus}" :value="name" @input="nameChange" @focus="hasFocus" @blur="lostFocus"/>
				<view class="text">
					好名字可以让你的朋友更容易记住你。
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				IsDisabled: true,
				name:'?',
				isFocus:false,
			}
		},
		mounted() {
				
		},
		methods: {
			//input值改变
			nameChange(e){
				console.log(e.detail.value)
				this.name = e.detail.value;
				if(e.detail.value == name && e.detail.value == ""){
					this.IsDisabled = true;
				}else{
					this.IsDisabled = false;
				}
			},
			//获取焦点
			hasFocus(e){
				this.isFocus = true;
			},
			//失去焦点
			lostFocus(e){
				this.isFocus = false;
			},
			//保存
			send(){
				let UserInfo = uni.getStorageSync('userInfo');
				UserInfo.name = this.name;
				uni.setStorageSync("userInfo",UserInfo)
				uni.showToast({
					title:'名字修改成功！',
					icon:"none"
				})
				console.log(uni.getStorageSync('userInfo'))
			}
		}
	}
</script>

<style lang="scss">
	.edit {
		width: 100%;
		height: auto;
		display: flex;
		flex-direction: column;

		.flex-end {
			width: 100%;
			height: 70rpx;
			display: flex;
			margin-bottom: 20rpx;
			justify-content: flex-end;
			position: relative;
			flex-direction: row-reverse;

			.btn {
				background-color: #4CD964;
				position: absolute;
				right: 4%;
				top: 10rpx;
			}

			.btn[disabled] {
				background-color: #C8C7CC;
				box-sizing: border-box;
				border: none;
			}
		}
		.flex-column{
			width: 100%;
			height: auto;
			display: flex;
			flex-direction: column;
			.name{
				width: 92%;
				height: 80rpx;
				display: flex;
				align-items: flex-start;
				border-bottom: 1rpx solid #C8C7CC;
				margin: 0 auto;
			}
			.borderbottom{
				border-bottom: 1rpx solid #4CD964;
			}
			.text{
				font-size: 24rpx;
				color: #808080;
				margin-left: 4%;
				margin-top: 20rpx;
			}
		}

	}
</style>
