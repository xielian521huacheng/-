<template>
	<view>
		
		<view>
			<!-- 模块1 -->
			<view class="distance">
				<view class="nav-item">
					<view class="text">姓名</view>
					<input type="text" style="width: 75%;margin-top:1%;" placeholder="收货人姓名"/>
				</view>

				<view class="nav-item">
					<text class="text">电话</text>
					<input type="number" style="margin-left: 8%;width: 75%;"  placeholder="收货人手机号"/>
				</view>
				<view class="nav-item" @click="showCityPicker">
					<text class="text" >地区</text>
					<text class="place" style="color: #4b4b4b;width: 80%;" placeholder="选择省/市/区" >{{ area }}</text>
					<text ></text>
					<image src="../../static/user/right-arrow.png" class="youjiantou"></image>
				</view>
				<view class="nav-item">
					<view class="content1">
						<text class="text1">详细地址</text>
						<input type="text" class="placeholder" placeholder="街道门牌、楼层房间号等信息" />
					</view>
				</view>
			</view>
			<!-- 模块2 -->

				<view class="nav-item">
					<view class="content" bind:tap="onTapQrCode">
						<text class="text">设为默认地址</text>

						<div class="switch">
							<label><input type="checkbox" name="checkboxswitch" class="onoff sw" checked /></label>
						</div>
					</view>
				</view>
				<view style="margin-top: 10%; ">
					<button class="save">保存</button>
				</view>
			</view>
			<mpvue-city-picker :themeColor="themeColor" ref="mpvueCityPicker" :pickerValueDefault="cityPickerValueDefault" @onConfirm="onConfirm"></mpvue-city-picker>
		</view>
	</view>
</template>

<script>
import mpvueCityPicker from '../../components/mpvue-citypicker/mpvueCityPicker.vue';
export default {
	data() {
		return {
			themeColor: '#007AFF',
			cityPickerValueDefault: [0, 0, 1],
			area: '',
			label: '',
		};
	},
	components: {
		mpvueCityPicker
	},
	//监听返回
	onBackPress() {
		if (this.$refs.mpvueCityPicker.showPicker) {
			this.$refs.mpvueCityPicker.pickerCancel();
			return true;
		}
	},
	//监听页面加载
	onUnload() {
		if (this.$refs.mpvueCityPicker.showPicker) {
			this.$refs.mpvueCityPicker.pickerCancel();
		}
	},
	onLoad() {
		// this.initData();
		let userInfo = this.user;
		if (userInfo) {
			this.area = userInfo.area;
			this.label = userInfo.label;
		}
	},
	computed: {
		labelText: {
			get() {
				return labelArray[this.label];
			},
			set(val) {}
		}
	},

	methods: {
		//显示三级联动城市组件
		showCityPicker() {
			this.$refs.mpvueCityPicker.show();
		},
		onConfirm(e) {
			this.area = e.label;
		},

		back() {
			uni.navigateTo({
				url: '/pages/my-shop/address/my_shop'
			});
		},
		//选择地址标签
		
	}
};
</script>

<style>
page {
	background-color: #eceff1;
}

.back-img {
	width: 40rpx;
	height: 40rpx;
	margin-top: 30%;
	margin-left: 30rpx;
}
.title {
	/* margin-top: 8%; */
	margin-left: 25%;
	font-size: 18px;
	/* margin:0rpx 40rpx 15rpx 190rpx */
}
.add {
	width: 40rpx;
	height: 40rpx;
	margin-top: 60%;
}

.address-book {
	height: 50rpx;
	width: 50rpx;
}
.nav-item {
	display: flex;
	justify-content: space-between;
	align-items: center;
	box-sizing: border-box;
	padding: 0 30rpx;
	min-height: 100rpx;
	background-color: #fff;
	border-bottom: 1rpx solid #eceff1;
}

.distance {
	margin-top: 2.8%;
}
.labelText {
	color: #4b4b4b;
	margin-left: 67%;
	font-size: 15px;
}

.content {
	font-size: 32rpx;
	line-height: 1.6em;
	flex: 1;
	display: flex;
	justify-content: space-between;
}
.content1 {
	height: 80px;
}

.text {
	color: #4b4b4b;
}
.text1 {
	color: #4b4b4b;

	/* margin-top: 90%; */
}
.place {
	margin-right: -35%;
}

.phone {
	text-align: right;
	margin-right: -2%;
	/* flex: 0.9; */
	color: #757575;
}
.youjiantou {
	height: 28rpx;
	width: 28rpx;
	text-align: center;
	margin-top: 1;
}
.choose {
	/* text-align: right; */
	margin-right: -60%;
	color: #757575;
}

.placeholder {
	margin-left: 50%;
	margin-top: -12%;
	width: 200%;
}

.save {
	background-color: #C40000;
	border-radius: 50px;
	width: 92%;
	color: #FFFFFF;
}
.onoff::before {
	content: '';
	display: block;
	width: 35px; /* 滑动范围设置 */
	height: 20px;
	border: 1px solid rgb(156, 155, 155);
	background-color: rgb(179, 176, 176);
	border-radius: 15px; /* 圆角设置 */
	margin-left: 75%; /* 位置的调整 */
	/* margin-top: 10px; */
}

.onoff::after {
	content: '';
	display: block;
	width: 19px; /* 按钮大小 */
	height: 19px;
	background-color: rgb(255, 255, 255);
	margin-left: 75.5%; /* 按钮位置调整 */
	margin-top: -24.37%;
	transition: margin 0.2s ease-in 0.2s; /* 变化速度与方式 */
	border-radius: 15px; /* 圆角设置 */
}
.onoff:checked::after {
	margin-left: 85.5%;
}

.switch .onoff:checked ~ label::after {
	background-color: rgb(87, 181, 131);
}
</style>
