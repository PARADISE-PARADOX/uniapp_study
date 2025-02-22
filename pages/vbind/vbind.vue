<template>
	<view>
		<image v-bind:src="picurl"></image>
	</view>
	
	<view class='box' :class="{active:isActive}">
		v-bind
	</view>
	<view class='box' :style="{width:'300px',height:size+'px'}">
		逐渐变长
	</view>
</template>

<script setup>
	import { ref } from 'vue';
	
	const isActive = ref(false)
	const size = ref(100)
	
	setInterval(()=>{
		isActive.value = !isActive.value;
		size.value+=10
	},1000)
	
	const picurl = ref("/static/2.1.png")
</script>

<style lang="scss">
.box{
	width: 200px;
	height: 40vh;
	background: red;
}

.active{
	width: 100px;
	height: 40vh;
	background: blue;
}
</style>
