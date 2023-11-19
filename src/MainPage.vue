<script setup>
import { Button, Space, Avatar } from 'ant-design-vue';
import config from './config.js';
const { tel } = config;
const defaultMessage = '我秦始皇！挪车！';
const moveCar = () => {
    window.location.href = `tel:${tel}#mp.weixin.qq.com`;
};
const postMessage = () => {
    window.location.href = `sms:${tel}?body=${defaultMessage}#mp.weixin.qq.com`;
};
</script>

<template>
    <div class="main-page flex items-center justify-center w-full h-full">
        <Space direction="vertical" align="center" :size="40">
            <Space>
                <Avatar class="avatar" :size="100" src="/avatar.jpeg"> </Avatar>
            </Space>
            <Space direction="vertical" :size="40">
                <Button @click="moveCar">电话挪车</Button>
                <Button @click="postMessage">短信挪车</Button>
            </Space>
            <Space wrap :size="40">
                <div class="h-[100px]"></div>
            </Space>
        </Space>
    </div>
</template>
