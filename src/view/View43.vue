<template>
  <h2>count:{{ count }}</h2>
  <h2>触发次数:{{ updateNumber }}</h2>
  <button @click="change1">+1</button>
  <button @click="change2">-1</button>
</template>

<script lang="ts" setup>

import {watchThrottled} from "@vueuse/core";
import {ref} from "vue";

const count = ref(100)

const updateNumber = ref(0);

function change1()
{
  count.value++
}

function change2()
{
  count.value--;
}

watchThrottled(count, () =>
{
  console.log(count.value)
  updateNumber.value++;
}, {throttle: 1000})


</script>

<style scoped>

</style>
