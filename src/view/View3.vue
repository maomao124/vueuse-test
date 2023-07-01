<template>

  <h1>{{ count }}</h1>
  <button @click="count++">+1</button>
  <br>
  <button @click="count--">-1</button>
  <br>
  <h1>最后一次更改时间：{{ new Date(lastChanged).toLocaleString() }}</h1>


</template>

<script setup lang="ts">

import {ref} from "vue";
import {useLastChanged} from "@vueuse/core";

const count = ref(100);

const lastChanged = useLastChanged(count)


</script>

<style scoped>

</style>
