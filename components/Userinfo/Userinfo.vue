<template>
	<view class='userInfo'>
		<image :src='userObj.avatar' class='avatar'></image>
		<view class='username'>{{userObj.name}}</view>
	</view>
</template>

<script setup>
// defineProps(['username','avatar'])

defineProps({
	userObj:{
		type:Object,
		defalut(){
			return {name:'匿名',avatar:'../../static/logo.png'}
		}
	} 
})
</script>

<style lang="scss" scoped>
.userInfo{
	width: 100%;
	height:200px;
	background: #ccc;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	image{
		width: 100px;
		height: 100px;
		border-radius: 50%;
	}
	.username{
		padding: 10px 0;
		font-size:20px;
	}
}
</style>