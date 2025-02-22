<template>
    <view class='totalTitle'>
        近期热梗
    </view>
    <view class='list'>
        <view class='row' v-for="(item,index) in lists" :key="item.id"> 
            <view class='text'>{{index+1}}.{{item.title}}</view>
            <view class='close' @click='closeHandler'>
                <icon type="clear" size='26'/>
            </view>
            
        </view>
    </view>
    <view class='ttlContent'>
        共{{lists.length}}条
    </view>
    <view class='row'>
        <input type='text' placeholder="输入热梗" v-model="iptValue"/>
        <button size='mini' type='primary' :disabled="!iptValue.length" @click="onSubmit">发布</button>
    </view>
    
</template>

<script setup>
import {ref} from 'vue'
const lists = ref([
    {id:1,title:'gannima'},
    {id:2,title:'caosinidema'},
    {id:3,title:'caonima'},
    {id:4,title:'shabi'},
])

const closeHandler = index =>{
    lists.value.splice(index,1)
}

const iptValue = ref("")

const onSubmit = ()=>{
    lists.value.push({id:Date.now(),title:iptValue.value})
    iptValue.value=''
}

</script>

<style>
.totalTitle{
    position: relative;
    font-size: 24px;
    display: flex;
    justify-content: center;
    padding:20px 0;
}    
    
.row{
    padding:10px 10px;
    display:flex;
    justify-content: space-between;
}   

.ttlContent{
    font-size: 16px;
    color:grey;
    display: flex;
    justify-content: center;
}

</style>