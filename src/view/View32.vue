<template>
  <h1>pageLeave:{{ pageLeave }}</h1>
</template>

<script lang="ts" setup>
import {usePageLeave} from "@vueuse/core";

const pageLeave = usePageLeave();

</script>

<style scoped>

</style>
