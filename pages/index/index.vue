<template>
	<view class="content">
		<view>---------------</view>
		<view>text标签</view>
			<text selectable>文本是否可选</text>
			<text space='emsp'>连续   空格</text>
			<text decode="true">是否解码</text>
			
			<scroll-view scroll-y='true' class='s1'>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
				<view>占位</view>
			</scroll-view>
			<scroll-view scroll-x='true' class='s1'>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
				<view class='box1'>测试</view>
			</scroll-view>
			<view>
				<swiper indicator-dots autoplay circular vertical>
					<swiper-item>1111</swiper-item>
					<swiper-item>1dawda11</swiper-item>
					<swiper-item>1dawdaw1</swiper-item>
					<swiper-item>1yjgy1</swiper-item>
				</swiper>
			</view>
			
			<view>
				<image src='/static/logo.png' class="pic1"></image>
			</view>
			
			<view>
				<swiper indicator-dots autoplay circular>
					<swiper-item><image src='/static/1e6494df9c0f042b6fbb8264959e4720.png' mode="aspectFill"></image></swiper-item>
					<swiper-item><image src='/static/2.1.png' mode="aspectFill"></image></swiper-item>
					<swiper-item><image src='/static/2.2.png' mode="aspectFill"></image></swiper-item>
					<swiper-item><image src='/static/2.1.2png.png' mode="aspectFill"></image></swiper-item>
				</swiper>
			</view>
			
			<Userinfo username='zyf' avatar="../../static/2.1.png"></Userinfo>
			<Userinfo avatar="../../static/2.2.png"></Userinfo>
			<Userinfo avatar="../../static/logo.png"></Userinfo>
			
			<view>------------------------------------</view>
			
			<Userinfo v-for="(item,index) in userinfo" :userObj='item'></Userinfo>
			
			
			
	</view>
</template>

<script setup>
import {ref} from 'vue'

const userinfo = ref([
	{name:'dwad',avatar:'../../static/2.1.png'},
	{name:'d453d',avatar:'../../static/2.2.png'},
	{name:'dwliuhg',avatar:'../../static/OIC.png'}
])
</script>

<style lang='scss'>
.s1{
	width: 80%;
	height: 220px;
	border: 1px solid red;
	white-space: nowrap;
	.box1{
		width: 200px;
		height: 100px;
		background-color: green;
		display: inline-block;
		margin: 5px;
	}
}
swiper{
	width: 100vw;
	height: 200px;
	border: 1px solid blue;
	swiper-item{
		width:100%;
		height: 100%;
		background: pink;
	}
	swiper-item:nth-child(2n){
		background: orange;
	}
}
.pic1{
	width: 100px;
	height: 100px;
}
</style>
