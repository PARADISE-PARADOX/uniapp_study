<template>
  <view class="">
	{{name}} ---- {{age}}
	<scroll-view scroll-y="true" ref="scroll"></scroll-view>
  </view>
  <view>计数{{count}}</view>
  <view v-for="item in 200">{{item}}</view>
  <view class='fixed' v-if='fixed'>↑</view>
</template>

<script setup>

import {ref} from 'vue'
import {onLoad,onReady,onShow,onHide,onUnload,onPageScroll} from '@dcloudio/uni-app'

const name =ref('zhangsan')
const age = ref(0)

const scroll = ref(null)

const count = ref(0)
const fixed = ref(false)

let time = setInterval(()=>{
	count.value++
},50)

// 用于监听页面的加载，调用时其参数为上个页面传递的数据
onLoad((e)=>{
	console.log('onload函数')
	console.log(e)
	name.value = e.name
	age.value = e.age
	
	console.log(scroll.value)
})

// 监听页面显示，页面每次出现在屏幕上都触发,包括从下级页面点返回露出当前页面
onShow(()=>{
	console.log('onShow函数')
	time = setInterval(()=>{
		count.value++
	},50)
})

// 监听的页面初次渲染完成，组件完成挂载
onReady(()=>{
	console.log('onReady函数')
	console.log(scroll.value)
})

// 监听页面隐藏，离开页面触发
onHide(()=>{
	console.log('onHide函数')
	clearInterval(time)
})

// 页面被关闭或者跳转到其他页面时触发，也会用于缓存清理
onUnload(()=>{
	console.log('onUnload函数')
})

onPageScroll((e)=>{
	console.log(e.scrollTop)
	if(e.scrollTop>1000){
		fixed.value=true;
	}else{
		fixed.value=false
	}
})

</script>

<style lang="scss" scoped>
.fixed{
	width: 100px;
	height: 100px;
	background-color: orange;
	position: fixed;
	right: 30px;
	bottom: 30px;
	justify-content: center;
}
</style>
