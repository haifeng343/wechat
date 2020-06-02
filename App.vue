<script>
	export default {
		//监听页面加载
		onLaunch: function() {
			// console.log('App Launch')
		},
		//监听页面显示
		onShow: function() {
			// console.log('App Show')
		},
		//监听页面隐藏
		onHide: function() {
			// console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	uni-tabbar .uni-tabbar__icon{
		width: 40rpx;
		height: 40rpx;
	}
	page{
		background-color: #f5f5f5;
	}
	uni-page-head {
		display: none;
	}
	.container{
		width: 100%;
		height: auto;
		font-size: 32rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		background-color: #fff;
	}
	.content{
		width: 100%;
		height: auto;
		box-sizing: border-box;
		padding: 0 4%;
	}
	a{
		color: #333333;
		text-decoration: none;
	}
</style>
