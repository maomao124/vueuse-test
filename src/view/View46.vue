<template>
  <h2>count:{{ count }}</h2>
</template>

<script lang="ts" setup>

import {get} from "@vueuse/core";
import {ref} from "vue";

const count = ref(200);

console.log(get(count))
</script>

<style scoped>
h2 {
  color: red;
}
</style>
