<template>
<div>
  <h2>acceleration:{{JSON.stringify(acceleration)}}</h2>
  <h2>accelerationIncludingGravity:{{JSON.stringify(accelerationIncludingGravity)}}</h2>
  <h2>rotationRate:{{JSON.stringify(rotationRate)}}</h2>
  <h2>interval:{{interval}}</h2>

</div>
</template>

<script lang="ts" setup>
import {useDeviceMotion} from "@vueuse/core";

const {
  acceleration,
  accelerationIncludingGravity,
  rotationRate,
  interval,
} = useDeviceMotion()

setTimeout(()=>
{
  console.log(acceleration.value?.x)
  console.log(acceleration.value?.y)
  console.log(acceleration.value?.z)
  console.log(accelerationIncludingGravity.value?.x)
  console.log(accelerationIncludingGravity.value?.y)
  console.log(accelerationIncludingGravity.value?.z)
  console.log(rotationRate.value?.alpha)
  console.log(rotationRate.value?.gamma)
  console.log(rotationRate.value?.beta)
},1000)

</script>

<style scoped>

</style>
