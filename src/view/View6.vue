<template>
  <div ref="dropZoneRef">
    文件放置位置
  </div>
</template>

<script setup lang="ts">
import {ref} from "vue";
import {useDropZone} from "@vueuse/core";

const dropZoneRef = ref<HTMLDivElement>()

function onDrop(files: File[] | null)
{
  if (files != null)
  {
    for (let file of files)
    {
      console.log(file);
    }
  }
}

const {isOverDropZone} = useDropZone(dropZoneRef, onDrop)

</script>

<style scoped>
div {
  background: dodgerblue;
  width: 600px;
  height: 600px;
  text-align: center;
}
</style>
