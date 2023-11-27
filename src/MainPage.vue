<script setup>
import { Button } from 'vant';
import config from './config.js';
import { PhoneOutlined, MessageOutlined, CopyrightOutlined } from '@vicons/antd';
const data = new URLSearchParams(window.location.search);
const tel = data.get('tel') || config.tel;
const message = data.get('message');
const moveCar = () => {
    window.location.href = `tel:${tel}`;
};
const postMessage = () => {
    window.location.href = `sms:${tel}${message || `?body=${message}`}`;
};
</script>

<template>
    <div
        class="main-page flex flex-col items-center justify-center w-full h-full py-[3vh] bg-[url('/cofe.jpeg')] bg-cover font-sans"
    >
        <div
            style="backdrop-filter: blur(8px)"
            class="flex-1 shadow-2xl rounded-xl w-[90vw] bg-white/20 flex items-center p-[30px] justify-around flex-col"
        >
            <div>
                <img src="/slogan.png" class="w-full" />
                <img src="/callme.png" class="w-full" />
            </div>
            <img src="/car.png" class="w-full" />
            <div class="w-full flex flex-col gap-8 items-center">
                <Button
                    class="w-[100px] h-[100px] shadow-2xl rounded-full bg-transparent border-[#323232] border-2 text-[#323232]"
                    style="backdrop-filter: blur(50px)"
                    @click="moveCar"
                >
                    <PhoneOutlined class="w-[35px]" />
                </Button>
                <Button
                    class="w-[180px] rounded-full bg-transparent border-[#323232] border-2 font-bold text-[#323232]"
                    style="backdrop-filter: blur(50px)"
                    @click="postMessage"
                >
                    <div class="flex items-center justify-center gap-2">
                        <MessageOutlined class="h-[18px]" />发送短信
                    </div>
                </Button>
            </div>
        </div>
        <div
            style="text-shadow: white 0 0 10px"
            class="flex py-[10px] flex-col justify-center items-center gap-1 flex-none text-[#323232] text-[12px]"
        >
            <p>
                备案号:&nbsp;
                <a
                    class="text-blue-950"
                    target="_blank"
                    href="https://beian.miit.gov.cn/"
                    rel="noreferrer"
                >
                    鄂ICP备2021009860号
                </a>
            </p>
            <p class="flex items-center justify-center gap-1">
                blackCell<CopyrightOutlined class="w-[12px]" />2021-present
            </p>
        </div>
    </div>
</template>
