<template>
  <h1>shift:{{ shift }}</h1>
  <h1>space:{{ space }}</h1>
  <h1>a:{{ a }}</h1>
  <h1>b:{{ b }}</h1>
  <h1>c:{{ c }}</h1>
  <h1>d:{{ magicKeys.d }}</h1>
  <h1>e:{{ magicKeys.e }}</h1>
  <h1>s:{{ magicKeys.s }}</h1>
  <h1>Shift+Ctrl+d:{{ magicKeys['Shift+Ctrl+d'] }}</h1>



</template>

<script lang="ts" setup>

import {useMagicKeys} from "@vueuse/core";

const {shift, space, a, b, c /* keys you want to monitor */} = useMagicKeys();

const magicKeys = useMagicKeys();


</script>

<style scoped>

</style>
