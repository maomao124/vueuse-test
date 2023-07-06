<template>
  <h1>是否空闲：{{ idle.idle }}</h1>
  <h1>最后活动时间：{{ t }}</h1>
</template>

<script lang="ts" setup>

import {useGeolocation, useIdle} from "@vueuse/core";
import {ref, watch} from "vue";

const idle = useIdle(10 * 1000); //10s
let t = ref();

watch(idle.lastActive, () =>
{
  t.value = new Date(idle.lastActive.value).toLocaleTimeString()
})


</script>

<style scoped>

</style>
