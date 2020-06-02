<template>
	<view class="content">
		<view class="text-area">
			<text class="title" @click="navto">{{title}}</text>
		</view>
		<view class="uni-padding-wrap uni-common-mt">
			<view class="uni-title uni-common-mt">
				flex-direction: row
				<text>\n横向布局</text>
			</view>
			<view class="uni-flex uni-row">
				<view class="flex-item uni-bg-red">A</view>
				<view class="flex-item uni-bg-green">B</view>
				<view class="flex-item uni-bg-blue">C</view>
			</view>
			<view class="uni-title uni-common-mt">
				flex-direction: column
				<text>\n纵向布局</text>
			</view>
			<view class="uni-flex uni-column">
				<view class="flex-item flex-item-V uni-bg-red">A</view>
				<view class="flex-item flex-item-V uni-bg-green">B</view>
				<view class="flex-item flex-item-V uni-bg-blue">C</view>
			</view>
		</view>
		<scroll-view :scroll-top="scrollTop" @scroll="scroll" @scrolltoupper="upper" @scrolltolower="lower" scroll-y="true"
		 class="scroll uni-flex uni-column">
			<view class="flex-item1 uni-bg-red">A</view>
			<view class="flex-item1 uni-bg-green">B</view>
			<view class="flex-item1 uni-bg-blue">C</view>
		</scroll-view>
		<button type="default" size="mini" @tap="goTop">回到顶部</button>
		<!-- <button type="primary" size="mini" open-type="getPhoneNumber"  @getphonenumber="getMobile">获取手机号</button> -->

		<view>
			<view class="uni-padding-wrap">
				<view class="page-section swiper">
					<view class="page-section-spacing">
						<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
							<swiper-item>
								<view class="swiper-item uni-bg-red">A</view>
							</swiper-item>
							<swiper-item>
								<view class="swiper-item uni-bg-green">B</view>
							</swiper-item>
							<swiper-item>
								<view class="swiper-item uni-bg-blue">C</view>
							</swiper-item>
						</swiper>
					</view>
				</view>
			</view>
			<view class="swiper-list">
				<view class="uni-list-cell uni-list-cell-pd">
					<view class="uni-list-cell-db">指示点</view>
					<switch :checked="indicatorDots" @change="changeIndicatorDots" />
				</view>
				<view class="uni-list-cell uni-list-cell-pd">
					<view class="uni-list-cell-db">自动播放</view>
					<switch :checked="autoplay" @change="changeAutoplay" />
				</view>
			</view>
			<view class="uni-padding-wrap">
				<view class="uni-common-mt">
					<text>幻灯片切换时长(ms)</text>
					<text class="info">{{duration}}</text>
				</view>
				<slider @change="durationChange" :value="duration" min="500" max="2000" />
				<view class="uni-common-mt">
					<text>自动播放间隔时长(ms)</text>
					<text class="info">{{interval}}</text>
				</view>
				<slider @change="intervalChange" :value="interval" min="2000" max="10000" />
			</view>
		</view>
		<movable-area class="area">
			<movable-view class="area-children" @change="movableChange" animation="true" :x="movable.x" :y="movable.y" direction="all">客服</movable-view>
		</movable-area>
		<view class="uni-padding-wrap uni-common-mt">
			<view class="text-box" scroll-y="true">
				<text class="text">{{text}}</text>
			</view>
			<view class="uni-btn-v">
				<button type="primary" :disabled="!canAdd" @click="add">add line</button>
				<button type="warn" :disabled="!canRemove" @click="remove">remove line</button>
			</view>
		</view>
		<view class="uni-list">
			<checkbox-group @change="checkboxChange">
				<label class="uni-list-cell uni-list-cell-pd" v-for="item in items" :key="item.value">
					<view>
						<checkbox :value="item.value" :checked="item.checked" />
					</view>
					<view>{{item.name}}</view>
				</label>
			</checkbox-group>
		</view>

		<view class="container">
			<editor id="editor" class="ql-container" show-img-resize="true" show-img-toolbar="true" placeholder="请输入富文本内容"
			 @input="hasInput"></editor>
		</view>

		<view class="uni-list-cell">
			<view class="uni-list-cell-left">
				当前选择
			</view>
			<view class="uni-list-cell-db">
				<picker mode="date" :value="date" @change="bindDateChange">
					<view class="uni-input">{{date}}</view>
				</picker>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		name: 'demo',
		data() {
			const currentDate = this.getDate({
				format: true
			})
			return {
				title: 'Hello', //头部
				scrollTop: 0, //距离顶部
				old: { //旧的顶部距离
					scrollTop: 0
				},
				indicatorDots: true, //显示指示点
				autoplay: true, //自动播放
				interval: 2000, //动画时长
				duration: 500, //动画间隔
				movable: { //客服初始位置
					x: 0,
					y: 200,
				},
				texts: [
					'HBuilder，200万开发者选择的IDE',
					'MUI，轻巧、漂亮的前端开源框架',
					'wap2app，M站快速转换原生体验的App',
					'5+Runtime，为HTML5插上原生的翅膀',
					'HBuilderX，轻巧、极速，极客编辑器',
					'uni-app，终极跨平台方案',
					'HBuilder，200万开发者选择的IDE',
					'MUI，轻巧、漂亮的前端开源框架',
					'wap2app，M站快速转换原生体验的App',
					'5+Runtime，为HTML5插上原生的翅膀',
					'HBuilderX，轻巧、极速，极客编辑器',
					'uni-app，终极跨平台方案'
				],
				text: '',
				canAdd: true,
				canRemove: false,
				extraLine: [],
				//复选框
				items: [{
						value: 'USA',
						name: '美国'
					},
					{
						value: 'CHN',
						name: '中国',
						checked: 'true'
					},
					{
						value: 'BRA',
						name: '巴西'
					},
					{
						value: 'JPN',
						name: '日本'
					},
					{
						value: 'ENG',
						name: '英国'
					},
					{
						value: 'FRA',
						name: '法国'
					}
				],
				checkArr: [], //选中的数据

				editorCtx: null, //接收富文本内容
				date: currentDate,
			}
		},
		onLoad() {

		},
		methods: {
			navto() {
				this.$router.push({
					path: '/pages/list/list',
					query: {
						id: 1
					}
				});
				uni.$emit('update', {
					msg: 'ddd'
				});
				uni.$on('update', function(data) {
					console.log(data)
				})
			},
			//滚动到顶部
			upper(e) {
				// console.log(e)
			},
			//滚动到底部
			lower(e) {
				// console.log(e)
			},
			//滚动事件
			scroll(e) {
				// console.log(e);
				this.old.scrollTop = e.detail.scrollTop;
			},
			//点击回到顶部
			goTop(e) {
				console.log(e)
				this.scrollTop = this.old.scrollTop;
				this.$nextTick(function() {
					this.scrollTop = 0
				})
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			},
			//获取手机号
			getMobile(e) {
				console.log(e)
			},
			//是否展示指示点
			changeIndicatorDots(e) {
				this.indicatorDots = e.detail.value;
			},
			//是否自动播放
			changeAutoplay(e) {
				this.autoplay = e.detail.value;
			},
			//幻灯片切换时长
			durationChange(e) {
				console.log(e)
				this.duration = e.detail.value;
			},
			//自动播放时长
			intervalChange(e) {
				console.log(e);
				this.interval = e.detail.value;
			},
			//客服按钮距离改变
			movableChange(e) {
				let width = window.innerWidth / 2;
				this.movable.x = 0;
				if (e.detail.x < width) {
					this.movable.x = 0;
					this.movable.y = e.detail.y;
				} else {
					this.movable.x = width * 2
					this.movable.y = e.detail.y;
				}
			},
			//添加内容
			add() {
				this.extraLine.push(this.texts[this.extraLine.length % 12]);
				this.text = this.extraLine.join('\n');
				this.canAdd = this.extraLine.length < 12;
				this.canRemove = this.extraLine.length > 0;
			},
			//删除内容
			remove() {
				if (this.extraLine.length > 0) {
					this.extraLine.pop();
					this.text = this.extraLine.join('\n');
					this.canAdd = this.extraLine.length < 12;
					this.canRemove = this.extraLine.length > 0;
				}
			},
			//复选框数据
			checkboxChange(e) {
				this.checkArr = e.detail.value;
			},
			//初始化加富文本内容赋值给变量
			hasInput(e) {
				this.editorCtx = e.detail.html;
			},
			//撤销
			bindDateChange(e) {
				this.date = e.detail.value;
			},
			//日期格式转换
			getDate(type) {
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;
				let day = date.getDate();

				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year + 2;
				}
				month = month > 9 ? month : '0' + month;;
				day = day > 9 ? day : '0' + day;
				return `${year}-${month}-${day}`;
			}
		}
	}
</script>

<style>
	.container {
		width: 100%;
		height: auto;
		display: flex;
		flex-direction: column;
	}

	.ql-container {
		width: 90%;
		height: 400rpx;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		border: 1rpx solid #8F8F94;
	}

	.scroll {
		width: 100%;
		height: 200rpx;
	}

	.uni-flex {
		display: flex;
		justify-content: flex-start;
	}

	.flex-item {
		width: 200rpx;
		height: 200rpx;
		color: #fff;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.flex-item1 {
		width: 100%;
		height: 200rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.uni-row {
		display: flex;
		flex-direction: row;
	}

	.uni-column {
		display: flex;
		flex-direction: column;
	}

	.uni-bg-red {
		background: #DD524D;
	}

	.uni-bg-green {
		background: #4CD964;
	}

	.uni-bg-blue {
		background: #007AFF;
	}

	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}

	.swiper {
		width: 100%;
		height: 400rpx;
	}

	.swiper-item {
		width: 100%;
		height: 100%;
	}

	.area {
		width: 100%;
		min-height: 100%;
		position: fixed;
		left: 0;
		top: 0;
	}

	.area-children {
		width: 100rpx;
		height: 100rpx;
		border-radius: 100%;
		font-size: 26rpx;
		color: black;
		background: #FFFFFF;
		box-shadow: 0 4rpx 4rpx 4rpx rgba(0, 0, 0, 0.2);
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.text {
		font-size: 26rpx;
	}
</style>
