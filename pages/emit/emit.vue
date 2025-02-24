<template>
  <view class="">
	<emit-child @add="onAdd"></emit-child>
	<view>num:{{num}}</view>
  </view>
</template>

<script setup>
	
import {ref} from 'vue'
const num = ref(0)
	
const onAdd = e =>{
	console.log(e)
	num.value = e
}

</script>

<style lang="scss" scoped>

</style>
