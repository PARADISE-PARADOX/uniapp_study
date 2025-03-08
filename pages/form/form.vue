<template>
    <view class='out'>
        <input type='text' :value='iptValue' @focus="isActive=true" @blur="isActive=false" @confirm="console.log(123)"/>
        <image src='/static/OIC.png' class='pic' :class="isActive?'active':''"> </image>
    </view>
    <view>yulan:{{iptValue}}</view>
</template>

<script setup>
import {ref} from 'vue'
const iptValue = ref('')
const isActive = ref(false);



</script>

<style>
.out{
    padding: 0 20px;
    margin-top: 40px;
    position:relative;
    input{
        border: 1px solid red;
        height: 40px;
        position:relative;
        z-index:2;
        background:#fff;
    }
}

.pic{
    width: 24px;
    height: 24px;
    z-index: 1;
    position: absolute;
    top:0px;
    left:calc(50% - 12px);
    transition: top 0.3s;
}

.pic.active{
    top:-24px;
}
</style>