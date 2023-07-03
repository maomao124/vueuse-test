<template>
  <button @click="toShare">点击分享</button>
</template>

<script lang="ts" setup>
import {useShare} from "@vueuse/core";

const share = useShare();

function toShare(): void
{
  if (share.isSupported)
  {
    share.share({
      title: "分享测试",
      text: "11111111111111111111111111111111111111",
      url: location.href
    })
  }
  else
  {
    console.log("不支持")
  }
}

</script>

<style scoped>

</style>
