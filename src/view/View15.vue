<template>

  剪切板内容：<br>
  <textarea v-text="clipboard.text"></textarea>
  <br>
  <input type="text" v-model="source">
  <br>
  <button @click="clipboard.copy(source)">点击复制</button>

</template>

<script lang="ts" setup>

import {useClipboard} from "@vueuse/core";
import {ref} from "vue";

const source = ref('Hello')
const clipboard = useClipboard({source});

</script>

<style scoped>

</style>
