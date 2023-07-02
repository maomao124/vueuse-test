<template>
  <h2>{{ location }}</h2>
</template>

<script setup lang="ts">
import {useBrowserLocation} from "@vueuse/core";
import {watch} from "vue";

const location = useBrowserLocation();
console.log(location.value)
watch(location, () =>
{
  console.log("监听到location更改")
  console.log(location)
})
</script>

<style scoped>

</style>
