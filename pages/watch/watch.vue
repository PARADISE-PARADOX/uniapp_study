<template>
  <view>
	<input type='text' v-model="person.name" />
  </view>
  {{person}}
</template>

<script setup>
import {ref, watch} from 'vue'
const person = ref({
	name:'zhansgan',
	age:23
})

// watch(person,(newValue,oldValue)=>{
// 	console.log(newValue)
// 	console.log(oldValue)
// })

watch(person,(newValue)=>{
	console.log(newValue)
},{deep:true,immediate:true})



</script>

<style lang="scss" scoped>

</style>
