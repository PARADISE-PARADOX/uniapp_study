<template>
  <view class="">
	<emit-child @add="onAdd" @change="onChange"></emit-child>
	<view class='box' :style="{background:color}">num:{{num}}</view>
  </view>
</template>

<script setup>
	
import {ref} from 'vue'
const num = ref(0)
const color = ref('#ccc')
	
const onAdd = e =>{
	console.log(e)
	num.value = e
	color.value = "#" + String(e).substring(4,7)
}

function onChange(e){
	console.log(e)
}

</script>

<style lang="scss" scoped>
.box{
	width: 100vw;
	height: 100px;
}

</style>
