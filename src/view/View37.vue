<template>
  <h2>output1:{{ output1 }}</h2>
  <h2>output2:{{ output2 }}</h2>
  <h2>output3:{{ output3 }}</h2>
  <h2>output4:{{ output4 }}</h2>
  <button @click="change">改变值</button>

</template>

<script lang="ts" setup>

import {TransitionPresets, useTransition} from "@vueuse/core";
import {ref} from "vue";

const source = ref(0)

const output1 = useTransition(source, {
  duration: 1000,
  transition: TransitionPresets.easeInOutCubic,
})
const output2 = useTransition(source, {
  duration: 500,
  transition: TransitionPresets.easeInOutCubic,
})
const output3 = useTransition(source, {
  duration: 5000,
  transition: TransitionPresets.easeInOutCubic,
})
const output4 = useTransition(source, {
  duration: 1000,
  transition: TransitionPresets.easeInCirc,
})

function change()
{
  source.value = source.value + 100
}

</script>

<style scoped>

</style>
