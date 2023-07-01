<template>
  <div>
    <div ref="el" :style="style" style="position: fixed">
      Drag me! I am at {{ x }}, {{ y }}
    </div>
  </div>
</template>

<script lang="ts" setup>

import {ref} from "vue";
import {useDraggable} from "@vueuse/core";

const el = ref<HTMLElement | null>(null)
const {x, y, style} = useDraggable(el, {
  initialValue: {x: 40, y: 40},
})


</script>

<style scoped>

div {
  background: #42b983;
}
</style>
