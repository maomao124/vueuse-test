<template>
  <h1>latitude:{{ coords.latitude }}</h1>
  <h1>altitude:{{ coords.altitude }}</h1>
  <h1>accuracy:{{ coords.accuracy }}</h1>
  <h1>heading:{{ coords.heading }}</h1>
  <h1>altitudeAccuracy:{{ coords.altitudeAccuracy }}</h1>
  <h1>longitude:{{ coords.longitude }}</h1>
  <h1>speed:{{ coords.speed }}</h1>

  <h1>locatedAt:{{ locatedAt }}</h1>
  <h1>error:{{ error }}</h1>

</template>

<script lang="ts" setup>

import {useGeolocation} from "@vueuse/core";

const {coords, locatedAt, error, resume, pause} = useGeolocation()

setTimeout(() =>
{
  console.log(coords.value)
}, 1000)

</script>

<style scoped>

</style>
