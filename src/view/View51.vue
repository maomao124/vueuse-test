<template>
  <h2>count:{{ count }}</h2>
  <h2>上一次的值:{{ previous }}</h2>
  <button @click="change1">+1</button>
  <button @click="change2">-1</button>
</template>

<script lang="ts" setup>

import {usePrevious} from "@vueuse/core";
import {ref} from "vue";

const count = ref(100)
const previous = usePrevious(count);

function change1()
{
  count.value++
}

function change2()
{
  count.value--;
}

</script>

<style scoped>

</style>
