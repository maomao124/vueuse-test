<template>
  <div>
    <button @click="bluetooth.requestDevice()">请求设备连接</button>
    <br>
    <h2>是否支持：{{ bluetooth.isSupported }}</h2>
    <br>
    <h2>是否连接：{{ bluetooth.isConnected }}</h2>
    <br>
    <h2>设备：{{ bluetooth.device }}</h2>
  </div>
</template>

<script lang="ts" setup>
import {useBluetooth} from "@vueuse/core";

const bluetooth = useBluetooth({acceptAllDevices: true,});
console.log(bluetooth);

</script>

<style scoped>

</style>
