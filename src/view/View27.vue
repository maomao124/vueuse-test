<template>
  <h1>FPS:{{ fps }}</h1>
</template>

<script lang="ts" setup>

import {useFps} from "@vueuse/core";

const fps = useFps();

setInterval(() =>
{
  console.log("时间" + new Date().toLocaleTimeString() + "  fps:" + fps.value)
}, 1000)

</script>

<style scoped>

</style>
