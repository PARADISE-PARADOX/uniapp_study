<template>
  <view class="layout">
	<expose-demo ref="child"></expose-demo>
  </view>
  <view>---------------------------</view>
  <button @click="onClick">修改</button>
  <navigator url='/pages/onload/onload?name=zgadaw&age=29'>跳转</navigator>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const child = ref(null)

onMounted(()=>{
	console.log(child.value)
})

const onClick = () =>{
	child.value.updateCount()
}

</script>

<style lang="scss" scoped>

</style>
