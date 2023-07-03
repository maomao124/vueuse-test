<template>
  <button @click="()=>{if (isSupported){show()}}">通知
  </button>
</template>

<script setup lang="ts">
import {useWebNotification} from "@vueuse/core";

const {
  isSupported,
  notification,
  show,
  close,
  onClick,
  onShow,
  onError,
  onClose,
} = useWebNotification({
  title: '你好，当前时间为' + new Date().toLocaleString(),
  dir: 'auto',
  lang: 'zh-cn',
  renotify: true,
  tag: '通知测试',
})
console.log(isSupported.value)
onClick((e) =>
{
  console.log("通知被点击了,点击的通知为", e.target.title)
})
onClose((e) =>
{
  console.log("通知被关闭了 ", e.target.title)
})


</script>

<style scoped>

</style>
