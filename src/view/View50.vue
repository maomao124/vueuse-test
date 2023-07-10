<template>
  <h2>original:{{ original }}</h2>
  <h2>cloned:{{ cloned.cloned }}</h2>
  <button @click="change">改变值</button>
</template>

<script lang="ts" setup>

import {ref} from "vue";
import {useCloned} from "@vueuse/core";

const original = ref({a: 1, b: 2, c: 3, d: {d1: 123, d2: {r: 678}}});

const cloned = useCloned(original);

function change()
{
  original.value.d.d2.r = 345552;
}

</script>

<style scoped>
h2 {
  color: red;
}
</style>
