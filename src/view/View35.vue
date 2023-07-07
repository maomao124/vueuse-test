<template>
  <h2>{{ now.toLocaleString() }}</h2>

</template>

<script lang="ts" setup>

import {useNow} from "@vueuse/core";

const {now, pause, resume} = useNow({controls: true})

</script>

<style scoped>

</style>
