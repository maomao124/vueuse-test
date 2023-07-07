<template>
  <h2>{{ count1 }}</h2>
  <h2>{{ count2 }}</h2>
  <h2>{{ count3 }}</h2>

</template>

<script lang="ts" setup>

import {useInterval} from "@vueuse/core";

const count1 = useInterval(200);
const count2 = useInterval(500);
const count3 = useInterval(1000);

</script>

<style scoped>

</style>
