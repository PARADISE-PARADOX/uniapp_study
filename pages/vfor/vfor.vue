<template>
  <view class="out">	
	<view class='box' v-for='(item,index) in 10' :key='index'>box模块{{index+1}}</view>
  </view>
  <view v-for="item in nba" :key='item.id'>
  	{{item.name}} -- {{item.age}}
  </view>
</template>

<script setup>
import {ref, watchEffect} from 'vue';
const nba = ref([
	{id:1,name:'man1',age:13},
	{id:2,name:'man2',age:65},
	{id:3,name:'man3',age:56},
	{id:4,name:'man4',age:24}
])

watchEffect(()=>{
	console.log(first)
})

</script>

<style lang="scss" scoped>

</style>
