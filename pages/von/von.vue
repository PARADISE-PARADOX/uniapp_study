<template>
	<view class='box' v-on:click="onClick">
		
	</view>
</template>

<script setup>
const onClick = () => console.log(123)

</script>

<style lang='scss'>
.box{
	width: 200px;
	height: 40vh;
	background: red;
}	       
</style>
