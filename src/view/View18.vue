<template>
  <img ref="img" src="public/favicon.ico" alt="图片">
  <br>
  <button @click="fullscreen.enter()">进入全屏</button>
</template>

<script setup lang="ts">
import {ref} from "vue";
import {useFullscreen} from "@vueuse/core";

const img = ref<HTMLImageElement>();

const fullscreen = useFullscreen(img);
console.log(fullscreen.isSupported.value);

</script>

<style scoped>
img {
  width: 300px;
  height: 300px;
  background: #42b983;
}
</style>
