<template>
<div>
  <h2>{{devices}}</h2>
  <h2>{{cameras}}</h2>
  <h2>{{microphones}}</h2>
  <h2>{{speakers}}</h2>

</div>
</template>

<script lang="ts" setup>
import {useDevicesList} from "@vueuse/core";

const {
  devices,
  videoInputs: cameras,
  audioInputs: microphones,
  audioOutputs: speakers,
} = useDevicesList()

</script>

<style scoped>

</style>
