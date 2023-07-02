<template>
  <div>
    <h1>{{ windowSize.width }}</h1>
    <h1>{{ windowSize.height }}</h1>
  </div>
</template>

<script setup lang="ts">
import {useWindowSize} from "@vueuse/core";

const windowSize = useWindowSize();

</script>

<style scoped>

</style>
