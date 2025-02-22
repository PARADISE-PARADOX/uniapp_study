<template>
	<view class="">
		<view v-if='shop'>is if </view>
		<view v-else='shop'>is else </view>
		<view v-if='day===1'>Mon </view>
		<view v-else-if='day===2'>Tue </view>
		<view v-else-if='day===3'>Wed </view>
		<view v-else-if='day===4'>Thu </view>
		<view v-else-if='day===5'>Fri </view>
		<view v-else-if='day===6'>Sat </view>
		<view v-else>Sun </view>
	</view>
	
	
	<!-- 显示v-if 不显示dom-->
	<view class='box' v-if="false"> 
	
		v-bind
	</view>
	<!-- 显示dom元素 -->
	<view class='box' v-show="false">
		v-bind
	</view>
</template>

<script setup>

import {ref} from "vue"
	
const shop = ref(true)
const day = ref(1)

setInterval(()=>{
	day.value%=7
	day.value++
	shop.value=!shop.value
},1000)

</script>

<style lang="scss" scoped>
.box{
	width: 200px;
	height: 40vh;
	background: red;
}	       
</style>
