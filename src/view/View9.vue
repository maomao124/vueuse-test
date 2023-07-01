<template>

  <h1>窗口是否聚焦：{{ windowFocus }}</h1>

</template>

<script setup lang="ts">

import {useWindowFocus} from "@vueuse/core";
import {watch} from "vue";

const windowFocus = useWindowFocus();


watch(windowFocus, (newValue) =>
{
  if (newValue)
  {
    console.log("窗口聚焦")
  }
  else
  {
    console.log("窗口取消聚焦")
  }
})

</script>

<style scoped>

</style>
