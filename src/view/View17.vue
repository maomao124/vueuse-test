<template>
  <div>
    <button ref="el" type="button">点击打开</button>
    <br>
    <br>
    <template v-if="files">
      <p>You have selected: <b>{{ `${files.length} ${files.length === 1 ? 'file' : 'files'}` }}</b></p>
      <li v-for="file of files" :key="file.name">
        {{ file.name }}
      </li>
    </template>
  </div>
</template>

<script setup lang="ts">
import {ref} from "vue";
import {useEventListener, useFileDialog} from "@vueuse/core";

const el = ref<HTMLButtonElement>();

const fileDialog = useFileDialog();
const files = fileDialog.files;
fileDialog.onChange((files) =>
{
  console.log("发生改变", files)
})

useEventListener(el, 'click', () =>
{
  fileDialog.open()
})

</script>

<style scoped>

</style>
