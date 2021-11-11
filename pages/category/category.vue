<template>
	<!-- <view class="goods_list">
		<view class="class" @click="click">
			<view class="item" data-id="uid1">分类1</view>
			<view class="item" data-id="uid2">分类2</view>
			<view class="item" data-id="uid3">分类3</view>
		</view>
		<scroll-view class="lists" :scroll-y="true" :scroll-with-animation="true" :scroll-into-view="current">
			<view id="uid1">
				<view class="title">分类1</view>
				<view v-for="(item,index) in 10" :key="index">分类1的：当前值{{item}}</view>
			</view>
			<view id="uid2">
				<view class="title">分类2</view>
				<view v-for="(item,index) in 10" :key="index">分类2的：当前值{{item}}</view>
			</view>
			<view id="uid3">
				<view class="title">分类3</view>
				<view v-for="(item,index) in 10" :key="index">分类3的：当前值{{item}}</view>
			</view>
		</scroll-view>
	</view> -->
	<category></category>
</template>

<script>
	import category from "../../components/category-s/category.vue"
	export default {
		data() {
			return {
				current:"uid3"
			}
		},
		components: {
			category
		},
		onLoad() {

		},
		methods: {
			click(e){
				this.current = e.target.dataset.id;
			}
		}
	}
</script>

<style>
	.goods_list{
		background-color: #FFFFFF;
		display: flex;
	}
	.goods_list .class{
		width: 20%;
		background-color: red;
	}
	.goods_list .class view{
		padding:10px;
		border:1px solid #ccc;
	}
	.goods_list .lists{
		width: 80%;
		height: 400px;
		background-color: #99fff9;
	}
	.goods_list .lists .title{
		font-size: 30px;
	}
</style>
