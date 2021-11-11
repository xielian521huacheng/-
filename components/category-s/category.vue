<template>
	<view class="content">
		<scroll-view scroll-y="true" class="SV_categoryTitle">
			<view class="categoryTitle">
				<view class="categoryName" v-for="(item,index) in categoryList" :key="index" :class="categoryNameActive == index?'categoryNameActive':''"
				 @click="categoryClickEvent(item,index)">
					{{item.name}}
				</view>
			</view>
		</scroll-view>
		<scroll-view class="scroll-Y" :scroll-y="true" :scroll-top="scrollTop" :scroll-with-animation="true" @scroll="scrollEvent">
			<view class="categoryList" v-for="(item,index) in categoryList" :key="item.id">
				<view class="categoryListName">
					<view class="categoryListName_line"></view>{{item.name}}
				</view>
				<view class="categoryListBox" v-for="(sub,idx) in item.subCategoryList" :key="idx">
					<image :src="sub.image" lazy-load mode=""></image>
					<text>{{sub.name}}</text>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				categoryList: [{
					"id": "1",
					"name": "女装 男装 穿搭",
					"subCategoryList": [{
						"id": "10",
						"name": "女装",
						image: "../../static/categories/female.jpg"
					}, {
						"id": "11",
						"name": "男装",
						image: "../../static/categories/male.jfif"
					}, {
						"id": "12",
						"name": "穿搭",
						image: "../../static/categories/chuanda.jfif"
					}]
				}, {
					"id": "2",
					"name": "家具 家饰 家纺",
					"subCategoryList": [{
						"id": "7",
						"name": "家具",
						image: "../../static/categories/jiaju.jpg"
					}, {
						"id": "8",
						"name": "家饰",
						image: "../../static/categories/jiafang.jfif",
					}, {
						"id": "9",
						"name": "家纺",
						image: "../../static/categories/jiashi.jfif",
					}]
				}, {
					"id": "3",
					"name": "运动 户外 乐器",
					"subCategoryList": [{
						"id": "4",
						"name": "运动",
						image: "../../static/categories/yundong.jpg",
					}, {
						"id": "5",
						"name": "户外",
						image: "../../static/categories/huwai.jfif",
					}, {
						"id": "6",
						"name": "乐器",
						image: "../../static/categories/yueqi.jfif",
					}]
				}],
				categoryNameActive: 3, //当前选中active
				scrollTop: 0, //scroll-top
				scrollVal: 0, //滑动的值
				scrollStatus: true, //点击状态，是否能点击
				nodeHeight: [], //存储categoryList的top
				windowHeight: 0,
				windowTop: 0,
			};
		},
		mounted() {
			uni.getSystemInfo({
				success: (res) => {
					this.windowHeight = res.windowHeight;
					this.windowTop = res.windowTop;
				}
			});
			this.nodeHeight = [];
			let theNode = uni.createSelectorQuery().in(this).selectAll(".categoryList");
			theNode.boundingClientRect((data) => {
				data.forEach((item, index) => {
					// #ifndef H5
					this.nodeHeight.push({
						top: item.top,
						index: index
					})
					// #endif
					// #ifdef H5
					this.nodeHeight.push({
						top: item.top + this.windowTop,
						index: index
					})
					// #endif
				})
			}).exec()
		},
		methods: {
			categoryClickEvent(item, index) {
				// 300毫秒才能执行下次点击
				if (this.scrollStatus) {
					this.scrollStatus = false;
					this.categoryNameActive = index;
					let theNode = uni.createSelectorQuery().in(this).selectAll(".categoryList");
					theNode.boundingClientRect((data) => {
						/* 获取当前第index的categoryList的top,滑动后值scrollVal + categoryList的top */
						// #ifndef H5
						this.scrollTop = this.scrollVal + data[index].top;
						// #endif
						// #ifdef H5
						this.scrollTop = this.scrollVal + data[index].top + this.windowTop;
						// #endif
						setTimeout(() => {
							// 200毫秒才能执行下次点击
							this.scrollStatus = true;
						}, 200)
					}).exec()
				}
			},
			scrollEvent(e) {
				if (this.scrollVal < e.detail.scrollTop) {
					// 向上
					this.nodeHeight.forEach(item => {
						if (this.scrollVal - item.top < 0 && this.scrollVal - item.top > -this.windowHeight) {
							this.categoryNameActive = item.index;
						}
					})
				} else {
					// 向下
					this.nodeHeight.forEach(item => {
						if (this.scrollVal - item.top > 0 && this.scrollVal - item.top < this.windowHeight) {
							this.categoryNameActive = item.index;
						}
					})
				}
				this.scrollVal = e.detail.scrollTop;
			},
		},
	}
</script>

<style>
	.categoryTitle {
		width: 249rpx;
		float: left;
		height: 100vh;
		border-right: 1px solid #ccc;
	}

	.SV_categoryTitle {
		width: 250rpx;
		height: 100vh;
		float: left;
	}

	.categoryName {
		width: 100%;
		text-align: center;
		height: 100rpx;
		line-height: 100rpx;
		color: #3E3E3E;
	}

	.categoryNameActive {
		background:#C40000;
	}

	.scroll-Y {
		height: 100vh;
		width: 500rpx;
		float: left;
	}

	.categoryList {
		width: 100%;
		padding-left: 16rpx;
		box-sizing: border-box;
		height: 100vh;
	}

	.categoryListName {
		width: 100%;
		height: 100rpx;
		line-height: 100rpx;
		text-indent: 20rpx;
		float: left;
	}

	.categoryListBox {
		width: 445rpx;
		border: 1px solid #CCCCCC;
		margin-right: 15rpx;
		float: left;
		overflow: hidden;
	}

	.categoryListBox image {
		width: 445rpx;
		height: 200rpx;
	}

	.categoryListName_line {
		height: 30rpx;
		background: #C40000;
		width: 8rpx;
		float: left;
		margin-top: 35rpx;
	}
</style>
