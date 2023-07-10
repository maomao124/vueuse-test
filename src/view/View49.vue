<template>
  文本：<br><input type="text" v-model="text">
  <br>
  文本转码后：<br>
  <textarea>{{base64.base64}}</textarea>
  <br>
  <br>
  图片：<br><img src="public/favicon.ico" ref="image" alt="图片">
  <br>
  图片转码后：<br>
  <textarea>{{base64Image.base64}}</textarea>
</template>

<script lang="ts" setup>

import {useBase64} from "@vueuse/core";
import {Ref, ref} from "vue";

const text = ref("hello");
const image = ref() as Ref<HTMLImageElement>

const base64 = useBase64(text);
const base64Image = useBase64(image);

</script>

<style scoped>

input, textarea {
  width: 50vw;
}
</style>
