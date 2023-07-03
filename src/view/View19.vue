<template>
  <template v-if="memory.memory">
    <div opacity="50">
      Used
    </div>
    <div>{{ size(memory.memory.usedJSHeapSize) }}</div>
    <div opacity="50">
      Allocated
    </div>
    <div>{{ size(memory.memory.totalJSHeapSize) }}</div>
    <div opacity="50">
      Limit
    </div>
    <div>{{ size(memory.memory.jsHeapSizeLimit) }}</div>
  </template>
</template>

<script setup lang="ts">
import {ref} from "vue";
import {useMemory} from "@vueuse/core";

const memory = useMemory();
console.log(memory.isSupported.value)

function size(v: number)
{
  const kb = v / 1024 / 1024
  return `${kb.toFixed(2)} MB`
}

</script>

<style scoped>
video {
  width: 300px;
  height: 300px;
  background: #42b983;
}
</style>
