<template>

  <h1>{{ count }}</h1>
  <button @click="count++">+1</button>
  <br>
  <button @click="count--">-1</button>


</template>

<script setup lang="ts">

import {onMounted, ref} from "vue";
import {useLastChanged, useStorage} from "@vueuse/core";

const count = ref(100);

const storage = useStorage("count", count);
//const storage = useStorage("count", count, sessionStorage);
onMounted(() =>
{
  setInterval(() =>
  {
    console.log(localStorage.getItem('count'));
  }, 1000)
})

</script>

<style scoped>

</style>
