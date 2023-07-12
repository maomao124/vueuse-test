<template>
  <svg ref="target"></svg>
  <br>
  颜色：<input type="color" v-model="color">
  <br>
  大小：<input type="number" v-model="size">
  <br>
  <button @click="undo">undo</button>
  <br>
  <button @click="redo">redo</button>
  <br>
  <button @click="clear">clear</button>

</template>

<script lang="ts" setup>

import {ref} from "vue";
import {useDrauu} from '@vueuse/integrations/useDrauu'
import {toRefs} from "@vueuse/core";

const target = ref()
const {undo, redo, canUndo, canRedo, clear, brush} = useDrauu(target)
const {color, size} = toRefs(brush)

</script>

<style scoped>
svg {
  width: 60vw;
  height: 60vh;
  background: blanchedalmond;
}
</style>
