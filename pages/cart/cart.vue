<template>
  <div class="cart-box">
    <s-header :title="'购物车'"></s-header>
    <view class="uni-list">
        <view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(value,key) in list" :key="key">
            <view class="uni-media-list">
                <view class="uni-media-list-logo">
                    <image v-if="showImg" :src="value.img"></image>
                </view>
                <view class="uni-media-list-body">
                    <view class="uni-media-titile">{{value.title}}</view>
                    <view class="uni-media-time">{{value.time}}</view>
                    <view class="uni-media-number">{{value.number}}</view>
                    <view class="uni-media-state">{{value.state}}</view>
                    <view class="uni-media-enter">{{value.enter}}</view>
                </view>
            </view>
        </view>
    </view>
	<!-- {image:'/static/logo.png',text:'成交列表'},
	{image:'/static/logo.png',text:'报名列表'},
	{image:'/static/logo.png',text:'收益列表'},
	{image:'/static/logo.png',text:'收货地址管理'},
	{image:'/static/logo.png',text:'帮助与客服'},
	{image:'/static/logo.png',text:'邀请注册'},
	{image:'/static/logo.png',text:'我要发活动'},
	{image:'/static/logo.png',text:'我的活动'}]" -->
	
  </div>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
				        title: "智能感应泡沫洗手机  活动招募",
				        time: "报名时间：3月19日00:00至3月21日00:00",
				        number: "报名人数：159/500",
				        state: "美国|黑科技",
				        enter: "我要报名",
				        // img: "/static/images/1.png"
				    },
				    {
				        title: "智能感应泡沫洗手机  活动招募",
				        time: "报名时间：3月19日00:00至3月21日00:00",
				        number: "报名人数：159/500",
				        state: "美国|黑科技",
				        enter: "我要报名",
				        // img: "/static/images/2.png"
				    },
				    {
				        title: "智能感应泡沫洗手机  活动招募",
				        time: "报名时间：3月19日00:00至3月21日00:00",
				        number: "报名人数：159/500",
				        state: "美国|黑科技",
				        enter: "我要报名",
				        // img: "/static/images/3.png"
				    },
				    {
				        title: "智能感应泡沫洗手机  活动招募",
				        time: "报名时间：3月19日00:00至3月21日00:00",
				        number: "报名人数：159/500",
				        state: "美国|黑科技",
				        enter: "我要报名",
				        // img: "/static/images/4.png"
				    },
				    {
				        title: "智能感应泡沫洗手机  活动招募",
				        time: "报名时间：3月19日00:00至3月21日00:00",
				        number: "报名人数：159/500",
				        state: "美国|黑科技",
				        enter: "我要报名",
				        // img: "/static/images/1.png"
				    }
				],
			}
		},
		methods: {
			
		}
	}
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
