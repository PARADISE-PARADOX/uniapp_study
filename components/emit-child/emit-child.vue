<template>
	<view>
		子组件
		<button @click="onClick">btn</button>
	</view>
	<view class='box'></view>
	<input type='text' @input='onInput' />
</template>

<script setup>
	
const emit = defineEmits(["add","change"])

function onClick(){
	emit('add',Math.random())
}

function onInput(e){
	console.log(e)
	emit('change',e.detail.value)
}
	
</script>

<style lang='scss' scoped>
	
input{
	border: 1px solid red;
	height: 40px;
}

</style>