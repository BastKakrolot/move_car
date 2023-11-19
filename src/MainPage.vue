<script setup>
import { Button, Space, Avatar } from 'ant-design-vue';
import config from './config.js';
const data = new URLSearchParams(window.location.search);
const tel = data.get('tel') || config.tel;
const message = data.get('message');
const defaultMessage = message || '我秦始皇！挪车！';
const moveCar = () => {
    window.location.href = `tel:${tel}`;
};
const postMessage = () => {
    window.location.href = `sms:${tel}?body=${defaultMessage}`;
};
</script>

<template>
    <div class="main-page flex flex-col items-center justify-center w-full h-full">
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
        <div
            class="flex mt-8 flex-col justify-center items-center gap-1 !text-default-600 dark:!text-default-500 font-extralight text-sm"
        >
            <p>
                备案号:&nbsp;
                <a
                    class="text-sm"
                    target="_blank"
                    href="https://beian.miit.gov.cn/"
                    rel="noreferrer"
                >
                    鄂ICP备2021009860号
                </a>
            </p>
            <p>blackCell&nbsp;2021-present</p>
        </div>
    </div>
</template>
