<template>
  <h1>请打开两个tab页</h1>
  <h2>是否支持：{{ broadcastChannel.isSupported }}</h2>
  <h2>是否关闭：{{ broadcastChannel.isClosed }}</h2>
  <button @click="send">点击发送消息</button>
  <button @click="broadcastChannel.close()">点击关闭</button>
</template>

<script setup lang="ts">
import {useBroadcastChannel} from "@vueuse/core";
import {watch} from "vue";

const broadcastChannel = useBroadcastChannel({name: 'test'});
console.log(broadcastChannel);

watch(broadcastChannel.data, (msg) =>
{
  console.log("接收到消息：" + msg)
})

function send()
{
  if (!broadcastChannel.isClosed.value)
  {
    console.log("发送消息")
    broadcastChannel.post("hello");
  }
}

</script>

<style scoped>

</style>
