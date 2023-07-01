<template>
  <div ref="el">
    更改窗口大小改变值<br>
    Height: {{ height }}<br>
    Width: {{ width }}
  </div>
</template>

<script setup lang="ts">

import {useElementSize} from "@vueuse/core";
import {ref} from "vue";

const el = ref(null)
const {width, height} = useElementSize(el)

</script>

<style scoped>

div {
  width: 100vw;
  height: 100vh;
}
</style>
