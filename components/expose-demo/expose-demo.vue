<template>
	<view>
		zizujian{{count}}
	</view>
</template>

<script setup>
import {ref} from 'vue'

const count = ref(100)
const updateCount = () => count.value++


defineExpose({
	count:count,
	updateCount:updateCount
})

</script>

<style>
view{
	background-color: #CCC;
	padding: 10px;
}
</style>