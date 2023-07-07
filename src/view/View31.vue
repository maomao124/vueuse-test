<template>
  <h1>isSupported:{{ network.isSupported }}</h1>
  <h1>type:{{ network.type }}</h1>
  <h1>isOnline:{{ network.isOnline }}</h1>
  <h1>saveData:{{ network.saveData }}</h1>
  <h1>rtt:{{ network.rtt }}</h1>
  <h1>downlink:{{ network.downlink }}</h1>
  <h1>downlinkMax:{{ network.downlinkMax }}</h1>
  <h1>effectiveType:{{ network.effectiveType }}</h1>
  <h1>offlineAt:{{ network.offlineAt }}</h1>
  <h1>onlineAt:{{ network.onlineAt }}</h1>
</template>

<script lang="ts" setup>
import {useNetwork} from "@vueuse/core";

const network = useNetwork();

</script>

<style scoped>

</style>
