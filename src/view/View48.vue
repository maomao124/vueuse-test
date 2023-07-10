<template>
</template>

<script lang="ts" setup>

import {get, set, useAsyncQueue} from "@vueuse/core";
import {ref} from "vue";

const p1 = (() =>
{
  return new Promise((resolve) =>
  {
    setTimeout(() =>
    {
      resolve(1000)
    }, 10)
  })
})

const p2 = ((result: number) =>
{
  return new Promise((resolve) =>
  {
    setTimeout(() =>
    {
      resolve(1000 + result)
    }, 20)
  })
})

const {activeIndex, result} = useAsyncQueue([p1, p2])

console.log(activeIndex.value)

console.log(result)
</script>

<style scoped>
h2 {
  color: red;
}
</style>
