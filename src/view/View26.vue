<template>
  <div>
    <video ref="video"
           muted
           autoplay
           controls></video>
    <br>
    <button @click="request">请求</button>
  </div>
</template>

<script lang="ts" setup>
import {useDevicesList, useDisplayMedia} from "@vueuse/core";
import {ref, watchEffect} from "vue";

const video = ref<HTMLVideoElement>()
const displayMedia = useDisplayMedia();

console.log(displayMedia.enabled.value)

watchEffect(() => {
  if (video.value)
    video.value.srcObject = displayMedia.stream.value!
})

function request()
{
  if (!displayMedia.isSupported.value)
  {
    console.log("不支持")
    return
  }
  if (displayMedia.enabled.value)
  {
    console.log('开启中，即将关闭')
    displayMedia.stop()
  }
  else
  {
    console.log("即将打开")
    displayMedia.start()
  }
}

</script>

<style scoped>

video {
  height: 600px;
  width: 900px;
}
</style>
