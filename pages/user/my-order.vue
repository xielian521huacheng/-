<template>
	<view>

		<!-- 分类 -->
		<Tabs :TabList="TabList" :currentTab="current" @tabs="tabsChange">
		<!-- 卡片 -->
			<!-- 1 -->
			<TabPane>
				<!-- 01 -->
				<view class="card">
					<view>
						<image src="../../static/user/my-order.png" class="shop"></image>
						<view class="text1">百果园</view>
						<view class="jiantou"><image src="../../static/user/my-order.png" class="youjiantou"></image></view>
						<view class="text2">已完成</view>
						<image src="../../static/user/my-order.png" class="goods_01"></image>
						<p class="title1">妃子笑荔枝：“一骑红尘妃子笑 ，无人知是荔枝来。”</p>
						<view class="price">￥20.00</view>
						<view class="specification">500g</view>
						<view class="quantity">x1</view>
						<button class="delete"><view style="top: -2%; font-size: 13px;">查看订单</view></button>
						<button class="confirm"><view style="top: -2%; font-size: 13px;">确认收货</view></button>
					</view>
				</view>

				<!-- 02 -->

				<view class="card">
					<view>
						<image src="../../static/user/my-order.png" class="shop"></image>
						<view class="text1">百果园</view>
						<view class="jiantou"><image src="../../static/user/my-order.png" class="youjiantou"></image></view>
						<view class="text2">已完成</view>
						<image src="../../static/user/my-order.png" class="goods_01"></image>
						<p class="title1">榴 莲：“何药能医肠九回， 榴莲不似蜀当归。”</p>
						<view class="price">￥50.00</view>
						<view class="specification">500g</view>
						<view class="quantity">x1</view>
						<button class="delete"><view style="top: -2%; font-size: 13px;">查看订单</view></button>
						<button class="confirm"><view style="top: -2%; font-size: 13px;">确认收货</view></button>
					</view>
				</view>
			</TabPane>
			<!-- 2 -->
			<TabPane>
				<view class="cancel"><text style="font-size: 17px; color: #868686;">暂无待付款的订单哦~</text></view>
			</TabPane>
			<!-- 3 -->
			<TabPane>
				<view class="cancel"><text style="font-size: 17px; color: #868686;">暂无待发货的订单哦~</text></view>
			</TabPane>
			<!-- 4 -->
			<TabPane>
				<!-- 01 -->
				<view class="card">
					<view>
						<image src="../../static/user/my-order.png" class="shop"></image>
						<view class="text1">百果园</view>
						<view class="jiantou"><image src="../../static/user/my-order.png" class="youjiantou"></image></view>
						<view class="text2">已完成</view>
						<image src="../../static/user/my-order.png" class="goods_01"></image>
						<p class="title1">妃子笑荔枝：“一骑红尘妃子笑 ，无人知是荔枝来。”</p>
						<view class="price">￥20.00</view>
						<view class="specification">500g</view>
						<view class="quantity">x1</view>
						<button class="delete"><view style="top: -2%; font-size: 13px;">查看订单</view></button>
						<button class="confirm"><view style="top: -2%; font-size: 13px;">确认收货</view></button>
					</view>
				</view>

				<!-- 02 -->

				<view class="card">
					<view>
						<image src="../../static/user/my-order.png" class="shop"></image>
						<view class="text1">百果园</view>
						<view class="jiantou"><image src="../../static/user/my-order.png" class="youjiantou"></image></view>
						<view class="text2">已完成</view>
						<image src="../../static/user/my-order.png" class="goods_01"></image>
						<p class="title1">榴 莲：“何药能医肠九回， 榴莲不似蜀当归。”</p>
						<view class="price">￥50.00</view>
						<view class="specification">500g</view>
						<view class="quantity">x1</view>
						<button class="delete"><view style="top: -2%; font-size: 13px;">查看订单</view></button>
						<button class="confirm"><view style="top: -2%; font-size: 13px;">确认收货</view></button>
					</view>
				</view>
			</TabPane>
			<!-- 5 -->
			<TabPane>
				<view class="cancel"><text style="font-size: 17px; color: #868686;">暂无已取消的订单哦~</text></view>
			</TabPane>
		</Tabs>
	</view>
</template>

<script>
import Tabs from '../../components/uni-tabs/tabs.vue'
import TabPane from '../../components/uni-tabs/tabPane.vue'
// import uniNavBar from '../../components/uni-nav-bar/uni-nav-bar.vue';
export default {
	data() {
		return {
			current: 0,
			TabList: [{ title: '全部' }, { title: '待付款' }, { title: '待发货' }, { title: '待收货' }, { title: '已取消' }]
		};
	},
	components: {

		Tabs,
		TabPane
	},
	methods: {
		tabsChange(index) {
			this.current = index;
		},
		back() {
			uni.switchTab({
				url: '/pages/user/user'
			});
		}
	}
};
</script>

<style>
.back-img {
	width: 40rpx;
	height: 40rpx;
	margin-top: 20%;
	margin-left: 30rpx;
}
.title {
	margin-top: -2.8%;
	margin-left: 32%;
	font-size: 20px;
}

.card {
	height: 170px;
	/* width: 350px; */
	border-radius: 5px;
	margin: 17px 12px 5px 12px;
	background-color: #ffffff;
	box-shadow: 0px 2px 5px #cdcdce;
}
.shop {
	height: 15px;
	width: 17px;
	margin: 15px 10px 0px 10px;
}
.text1 {
	font-size: 16px;
	margin-top: -62rpx;
	margin-left: 10%;
}
.youjiantou {
	height: 15px;
	width: 15px;
}
.jiantou {
	margin-top: -46rpx;
	margin-left: 26%;
}
.text2 {
	margin-top: -8%;
	margin-left: 85%;
	color: #C40000;
}
.goods_01 {
	height: 80px;
	width: 80px;
	border-radius: 5px;
	margin: 10px 10px 0px 12px;
}
.title1 {
	width: 150px;
	margin-top: -25%;
	margin-left: 30%;
	line-height: 18px;
}
.price {
	margin-top: -16%;
	margin-left: 83%;
}
.specification {
	margin-top: 8.5%;
	margin-left: 30%;
	font-size: 12px;
	color: #aeaeae;
}
.quantity {
	margin-top: -15%;
	margin-left: 93%;
	font-size: 12px;
	color: #aeaeae;
}
.delete {
	height: 25px;
	width: 80px;
	margin: 14% 47%;
}
.confirm {
	height: 25px;
	width: 80px;
	margin: -20.8% 74%;
	color: #ffffff;
	background-color: #c40000;
}
.cancel {
	margin-left: 30%;
	position: relative;
	margin-top: 30%;
}
</style>