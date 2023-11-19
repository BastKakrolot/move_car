<script setup>
import { Button } from 'vant';
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
    <div
        class="main-page flex flex-col items-center justify-center w-full h-full py-[3vh] bg-[url('/cofe.jpeg')] bg-cover font-sans">
        <div style="backdrop-filter: blur(8px);"
            class="flex-1 shadow-2xl rounded-xl w-[90vw] bg-white/20 flex  items-center p-[30px] justify-around flex-col">
            <div>
                <img src="/slogan.png" class="w-full" />
                <img src="/callme.png" class="w-full" />
            </div>
            <img src="/car.png" style="transform: scaleX(-1);" class="w-full scale-x-[-1]" />
            <div class="w-full flex flex-col gap-8">
                <Button class="w-full shadow-2xl" color="#323232" style="backdrop-filter: blur(8px);" @click="moveCar">电话：{{
                    tel
                }}</Button>
                <Button class="w-full" color="#454545" style="backdrop-filter: blur(8px);" @click="postMessage">短信</Button>
            </div>
        </div>
        <div class="flex py-[10px] flex-col justify-center items-center gap-1 flex-none text-black/70 text-[12px]">
            <p>
                备案号:&nbsp;
                <a class="text-blue-950" target="_blank" href="https://beian.miit.gov.cn/" rel="noreferrer">
                    鄂ICP备2021009860号
                </a>
            </p>
            <p>blackCell&nbsp;2021-present</p>
        </div>
    </div>
</template>
