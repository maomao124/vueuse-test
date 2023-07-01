<template>

  <h1>{{ count }}</h1>
  <button @click="count++">+1</button>
  <br>
  <button @click="count--">-1</button>
  <br>
  <button @click="undo">undo</button>
  <br>
  <button @click="redo">redo</button>

</template>

<script setup lang="ts">

import {ref} from "vue";
import {useDebouncedRefHistory} from "@vueuse/core";

const count = ref(100);
const {history, undo, redo} = useDebouncedRefHistory(count, {deep: true, debounce: 500});

</script>

<style scoped>

</style>
