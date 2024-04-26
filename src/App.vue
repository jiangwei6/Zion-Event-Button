<script setup lang="ts">
import EventButton from "./components/EventButton.vue";
import { reactive } from "vue";

const globalData = reactive({ value: "http://shipin.cdxyhpx.com/sv/3bba3a21-18926843f74/3bba3a21-18926843f74.mp4" });
const setGlobalData = (obj: any) => {
  globalData.value = obj.value;
}

</script>
<template>
  <EventButton public_id="123" vara="a"  varb="b"  btn_str="测试按钮" :global-data="globalData"
    :set-global-data="setGlobalData" />
</template>

<style>
#app{
  height: 60vh;
}
</style>
