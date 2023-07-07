<template>
  <h2>timestamp:{{ timestamp }}</h2>

</template>

<script lang="ts" setup>

import {useTimestamp} from "@vueuse/core";

const timestamp = useTimestamp();

</script>

<style scoped>

</style>
