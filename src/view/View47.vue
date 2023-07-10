<template>
  <h2>count:{{ count }}</h2>
  <button @click="change">改变值</button>
</template>

<script lang="ts" setup>

import {get, set} from "@vueuse/core";
import {ref} from "vue";

const count = ref(200);

console.log(get(count))

function change()
{
  set(count, get(count) + 1)
}

</script>

<style scoped>
h2 {
  color: red;
}
</style>
