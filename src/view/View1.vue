<template>
  <h1>鼠标位置：{{ x }},{{ y }}</h1>
</template>

<script lang="ts" setup>
import {useMouse} from "@vueuse/core";

const {x, y} = useMouse();

</script>

<style scoped>

</style>
