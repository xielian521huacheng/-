<template>
	<view>
		<view>
			<header class="home-header wrap" :class="{ active: headerScroll }">
			    <!-- 点击搜索框跳转到分类页 -->
				<router-link tag="i" to="./category">
					<image src="../../static/index/more-line.png" style="width: 55rpx; height: 55rpx; margin-top: 20rpx;"></image>
				</router-link>
				<!-- 搜索框 -->
				<div class="header-search" style="margin-top: -95rpx; margin-left: 70rpx;">
					<span class="app-name">衣饰商城</span>
					<image src="../../static/index/search.png" style="width: 55rpx; height: 55rpx;"></image>
					<router-link tag="span" class="search-title" to="./product-list">山河无恙，人间皆安</router-link>
				</div>
				<div style="margin-top: -88rpx;">
					<router-link class="login" tag="span" to="./login" v-if="!isLogin">
						登录
					</router-link>
					<router-link class="login" tag="span" to="./user" v-else>
						<van-icon name="manager-o" />
					</router-link>
				</div>
			</header> 
		</view>
		<swiper :list="swiperList"></swiper>
		<div class="category-list">
		  <div v-for="item in categoryList" v-bind:key="item.categoryId">
		    <img :src="item.imgUrl">
		    <span>{{item.name}}</span>
		  </div>
		</div>
		<view class="good">
		    <header class="good-header">热门商品</header>
		    <view class="good-box">
		      <view class="good-item" v-for="item in hots" :key="item.goodsId" @click="goToDetail(item)">
		        <img :src="`//lmall.xinfeng.site${item.goodsCoverImg}`" />
		        <view class="good-info">
		          <p class="name">{{item.goodsName}}</p>
		          <p class="subtitle">{{item.goodsIntro}}</p>
		          <span class="price">￥ {{item.sellingPrice}}</span>
		        </view>
		      </view>
		    </view>
		</view>
		<view class="good" :style="{ paddingBottom: '100px'}">
		    <header class="good-header">最新推荐</header>
		    <view class="good-box">
		      <view class="good-item" v-for="item in recommends" :key="item.goodsId" @click="goToDetail(item)">
		        <img :src="`//lmall.xinfeng.site${item.goodsCoverImg}`" />
		        <view class="good-info">
		          <p class="name">{{item.goodsName}}</p>
		          <p class="subtitle">{{item.goodsIntro}}</p>
		          <span class="price">￥ {{item.sellingPrice}}</span>
		        </view>
		      </view>
		      <!-- <div class="good-item" v-for="item in recommends" :key="item.goodsId" @click="goToDetail(item)">
		        <img :src="`//lmall.xinfeng.site${item.goodsCoverImg}`" alt="">
		        <div class="good-desc">
		          <div class="title">{{ item.goodsName }}</div>
		          <div class="price">¥ {{ item.sellingPrice }}</div>
		        </div>
		      </div> -->
		    </view>
		</view>
	</view>
</template>

<script>
	import swiper from '@/components/user/Swiper'
	export default {
		data() {
			return {
				swiperList: [],
				categoryList: [
					{
						name: '楼楼交友',
						imgUrl: '//s.yezgea02.com/1598679532890/jiaoyou.png',
						categoryId: 100001
					}, {
						name: '楼楼家政',
						imgUrl: '//s.yezgea02.com/1598679532890/jiazheng.png',
						categoryId: 100003
					}, {
						name: '楼楼水产',
						imgUrl: '//s.yezgea02.com/1598679734813/shuichan1.png',
						categoryId: 100002
					}, {
						name: '楼楼租车',
						imgUrl: '//s.yezgea02.com/1598679532890/zuche.png',
						categoryId: 100004
					}, {
						name: '楼楼招聘',
						imgUrl: '//s.yezgea02.com/1598679792590/pin.png',
						categoryId: 100005
					}, {
						name: '楼楼二手',
						imgUrl: '//s.yezgea02.com/1598679853415/ershou.png',
						categoryId: 100006
					}, {
						name: '楼楼宠物',
						imgUrl: '//s.yezgea02.com/1598679532890/chongwu.png',
						categoryId: 100007
					}, {
						name: '楼楼外卖',
						imgUrl: '//s.yezgea02.com/1598679905787/wm.png',
						categoryId: 100008
					}, {
						name: '楼楼电器',
						imgUrl: '//s.yezgea02.com/1598680199443/dianqi.png',
						categoryId: 100009
					}, {
						name: '楼楼充值',
						imgUrl: '//s.yezgea02.com/1598680264015/czcz.png',
						categoryId: 1000010
					}
				],
				sLogin: false,
				headerScroll: false,
				hots: [],
				newGoodses: [],
				recommends: [],
			}
		},
		components: {
			swiper
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="less" scoped>
	@import '../../common/style/mixin';
.home-header {
    position: fixed;
    left: 0;
    top: 0;
    line-height: 50px;
    padding: 0 15px;
    font-size: 15px;
    color: #fff;
    z-index: 10000;
}
.header-search {
    display: flex;
    line-height: 20px;
    padding: 5px 0;
    color: #232326;
    background: rgba(255, 255, 255, 0.7);
    border-radius: 20px;
}
.app-name {
    padding: 0 10px;
    color:  #c40000;
    font-size: 20px;
    font-weight: bold;
    border-right: 1px solid #666;
}
.search-title {
    font-size: 12px;
    color: #666;
    line-height: 29px;
}
.login {
    color:  #c40000;
	margin-left: 600rpx;
}
.van-icon-manager-o {
    font-size: 20px;
    vertical-align: -3px;
}
.img {
	height: 90rpx;
	width:90rpx;
	margin: 47rpx;
}
.text {
	margin-left: -120rpx;
}
.category-list {
    display: flex;
    flex-shrink: 0;
    flex-wrap: wrap;
    width: 100%;
    padding-bottom: 13px;
    div {
      display: flex;
      flex-direction: column;
      width: 20%;
      text-align: center;
      img {
        .wh(40px, 40px);
        margin: 13px auto 8px auto;
      }
    }
  }
.good {
    .good-header {
      background: #f9f9f9;
      height: 50px;
      line-height: 50px;
      text-align: center;
      color: @primary;
      font-size: 16px;
      font-weight: 500;
    }
    .good-box {
      display: flex;
      justify-content: flex-start;
      flex-wrap: wrap;
      .good-item {
          .fj();
          width: 100%;
          height: 120px;
          padding: 10px 0;
          border-bottom: 1px solid #dcdcdc;
          img {
            width: 140px;
            height: 120px;
            padding: 0 10px;
            .boxSizing();
          }
        .good-info {
            width: 56%;
            height: 120px;
            padding: 5px;
            text-align: left;
            .boxSizing();
            p {
              margin: 0
            }
            .name {
              width: 100%;
              max-height: 40px;
              line-height: 20px;
              font-size: 15px;
              color: #333;
              overflow: hidden;
              text-overflow:ellipsis;
              white-space: nowrap;
            }
            .subtitle {
              width: 100%;
              max-height: 20px;
              padding: 10px 0;
              line-height: 25px;
              font-size: 13px;
              color: #999;
              overflow: hidden;
            }
            .price {
              color: @primary;
              font-size: 16px;
            }
        }
      }
    }
  }
  .floor-list {
      width: 100%;
      padding-bottom: 50px;
      .floor-head {
        width: 100%;
        height: 40px;
        background: #F6F6F6;
      }
      .floor-content {
        display: flex;
        flex-shrink: 0;
        flex-wrap: wrap;
        width: 100%;
        .boxSizing();
        .floor-category {
          width: 50%;
          padding: 10px;
          border-right: 1px solid #dcdcdc;
          border-bottom: 1px solid #dcdcdc;
          .boxSizing();
          &:nth-child(2n) {
            border-right: none;
          }
          p {
            font-size: 17px;
            color: #333;
            &:nth-child(2) {
              padding: 5px 0;
              font-size: 13px;
              color: @primary;
            }
          }
          .floor-products {
            .fj();
            width: 100%;
            img {
              .wh(65px, 65px);
            }
          }
      }
    }
  }
</style>
