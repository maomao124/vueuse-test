<template>
  <h2>charging: {{charging}}</h2>
  <h2>chargingTime: {{chargingTime}}</h2>
  <h2>dischargingTime: {{dischargingTime}}</h2>
  <h2>level: {{level}}</h2>

</template>

<script lang="ts" setup>
import {useBattery} from "@vueuse/core";

const {charging, chargingTime, dischargingTime, level} = useBattery()

setTimeout(()=>
{
  console.log(charging.value)
  console.log(chargingTime.value)
  console.log(dischargingTime.value)
  console.log(level.value)
},500)

</script>

<style scoped>

</style>
