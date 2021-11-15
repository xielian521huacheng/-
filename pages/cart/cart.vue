<template>
	<div class="cart-box">
		<s-header :title="'购物车'"></s-header>
		<view class="uni-list">
			<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(value, key) in list" :key="key">
				<view class="uni-media-list">
					<view class="uni-media-list-logo"><image v-if="showImg" :src="value.img"></image></view>
					<view class="uni-media-list-body">
						<image src="/pages/static/cart/product.jpg"></image>
						<view class="uni-media-titile">{{ value.title }}</view>
						<view class="uni-media-state">{{ value.state }}</view>
						<view class="uni-media-number">{{ value.number }}</view>
						<view class="uni-media-enter">{{ value.enter }}</view>
					</view>
				</view>
			</view>
		</view>
	</div>
</template>

<script>
export default {
	data() {
		return {
			list: [
				{
					title: '【十三余 小豆蔻儿】[麒麟幻梦',
					state: 'S码一套',
					number: '数量：1',
					enter: '我要报名',
					image: '/pages/static/user/about-us.png'
				},
				{
					title: '【十三余 小豆蔻儿】[麒麟幻梦',
					state: 'S码一套',
					number: '数量：1',
					enter: '我要报名',
					image: '/pages/static/user/about-us.png'
				},
				{
					title: '【十三余 小豆蔻儿】[麒麟幻梦',
					state: 'S码一套',
					number: '数量：1',
					enter: '我要报名',
					image: '/pages/static/user/about-us.png'
				},
				{
					title: '【十三余 小豆蔻儿】[麒麟幻梦',
					state: 'S码一套',
					number: '数量：1',
					enter: '我要报名',
					image: '/pages/static/user/about-us.png'
				},
				{
					title: '【十三余 小豆蔻儿】[麒麟幻梦',
					state: 'S码一套',
					number: '数量：1',
					enter: '我要报名',
					image: '/pages/static/user/about-us.png'
				}
			]
		};
	},
	methods: {}
};
</script>

<style>
/* container start */
.uni-media-list {
	display: flex;
	margin: 50upx 20upx;
}

.uni-media-list-logo image {
	width: 220upx;
	height: 220upx;
}

.uni-media-list-body {
	width: 426upx;
	height: 249upx;
	margin-left: 50upx;
	display: flex;
	flex-direction: column;
	justify-content: space-around;
	margin-top: -20upx;
}

.uni-media-titile {
	width: 389upx;
	height: 27upx;
	font-family: PingFang-SC-Regular;
	font-size: 28upx;
	font-weight: normal;
	font-stretch: normal;
	line-height: 35upx;
	letter-spacing: 0px;
	color: #333333;
}

.uni-media-time {
	width: 450upx;
	height: 21upx;
	font-family: PingFang-SC-Regular;
	font-size: 22upx;
	font-weight: normal;
	font-stretch: normal;
	line-height: 35upx;
	letter-spacing: 0px;
	color: #666666;
}

.uni-media-number {
	width: 250upx;
	height: 21upx;
	font-family: PingFang-SC-Regular;
	font-size: 22upx;
	font-weight: normal;
	font-stretch: normal;
	line-height: 35upx;
	letter-spacing: 0px;
	color: #666666;
}

.uni-media-state {
	width: 142upx;
	height: 23upx;
	font-family: PingFang-SC-Regular;
	font-size: 24upx;
	font-weight: normal;
	font-stretch: normal;
	line-height: 35upx;
	letter-spacing: 0px;
	color: #999999;
}

.uni-media-enter {
	width: 128upx;
	height: 35upx;
	font-family: SourceHanSansCN-Light;
	font-size: 24upx;
	font-weight: normal;
	font-stretch: normal;
	line-height: 35upx;
	text-align: center;
	letter-spacing: 0px;
	color: #e90028;
	border: 1upx solid #e90028;
}

.uni-media-enter:hover {
	background-color: red;
	color: white;
}
</style>
