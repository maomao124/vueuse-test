<template>
  <h2>count:{{ count }}</h2>
  <button @click="change">改变值</button>
</template>

<script lang="ts" setup>

import {invoke, until, useCounter} from "@vueuse/core";
import {ref} from "vue";

const {count} = useCounter(10)

function change()
{
  count.value++;
}

invoke(async () =>
{
  await until(count).toMatch(v => v >= 20)
  alert('大于等于20')
})

</script>

<style scoped>

</style>
