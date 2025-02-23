<template>
  <view>
	<input type='text' v-model="person.name" />
  </view>
  {{person}}
  
  <input type='text' v-model='firstName' placeholder="名"/>
  <input type='text' v-model='lastName' placeholder="姓"/>
  <view> 全称 {{fullName}} </view>
</template>

<script setup>
import {ref, watch, watchEffect} from 'vue'
const person = ref({
	name:'zhansgan',
	age:23
})

const firstName = ref('man')
const lastName = ref('say')
const fullName = ref('')

// watch(person,(newValue,oldValue)=>{
// 	console.log(newValue)
// 	console.log(oldValue)
// })

watch(person,(newValue)=>{
	console.log(newValue)
},{deep:true,immediate:true})

watchEffect(()=>{
	console.log(firstName.value,lastName.value)
})




</script>

<style lang="scss" scoped>

</style>
