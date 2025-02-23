<template>
  <view class="out">
	<checkbox-group @change="itemChange">
		<view class='item' v-for="(item,index) in goods" :key='item.id'>
			<checkbox :value='item.id' :checked="item.checked"></checkbox> 
			<text class='title'>{{item.name}}</text>
			<text class='price'>{{item.price}}</text>
			<text class='del' @click="remove(index)">删除</text>
		</view>
	</checkbox-group>
	
	<view class='card'>
		<view class='text'>选中	{{totalNumber}}个产品，总价{{totalPrice}}元</view>
	</view>


  </view>
</template>

<script setup>
	
import {ref,computed} from 'vue'
const goods=ref([
	{id:'1',name:'xiaomi',price:3999,checked:false},
	{id:'2',name:'huawei',price:9999,checked:false},
	{id:'3',name:'vivo',price:4999,checked:false},
	{id:'4',name:'oppo',price:2999,checked:false},
	{id:'5',name:'iphone',price:12999,checked:false},
])

const selectGroup = ref([]);
const totalNumber = computed(()=>selectGroup.value.length)
const totalPrice = computed(()=>goods.value.filter(item=>item.checked).reduce((prev,current,index)=>prev + current.price,0))

const remove = index => {
	goods.value.splice(index,1)
}

const itemChange = e =>{
	selectGroup.value = e.detail.value;
	goods.value.forEach(item=>{
		item.checked = selectGroup.value.includes(item.id)
	})
}


</script>

<style lang="scss" scoped>

.out{
	padding:10px;
	.item{
		padding:10px 0;
		.price{
			margin-left: 30px;
		}
		.del{
			color:#c00;
			margin-left: 30px;
		}
	}
	.card{
		border-top: 1px solid #eee;
		margin-top: 30px;
		padding: 10px 0;
	}
}

</style>
