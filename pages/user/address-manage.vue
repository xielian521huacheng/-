<template>
	<view>
		<view class="container"></view>
		<view class="card">
		<button class="add" @click="newAddress">新增地址</button>	
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
			newAddress() {
				uni.navigateTo({
					url:"./newAddress"
				})
			}
		}
	}
</script>

<style>
.container {
	position: relative;
	height: 100%;
}
.card {
	position: absolute;
	margin-top: 180%;
	bottom: 0;
	width: 100%;
	height: 55px;/*脚部的高度*/
	background: #FFFFFF;
	border-top: 1rpx solid #cbcbcb; 
}
.add {
	/* display: flex; */
	background-color: #C40000;
	color: #FFFFFF;
	border-radius: 25px;
	margin-top: 5px;
	}
</style>
