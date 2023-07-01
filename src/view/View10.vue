<template>
  <div class="div">
    <h1>
      {{ windowScroll.x }}<br>
      {{ windowScroll.y }}
    </h1>
  </div>
</template>

<script lang="ts" setup>

import {useWindowScroll} from "@vueuse/core";
import {watch} from "vue";

const windowScroll = useWindowScroll();

watch(windowScroll.x, () =>
{
  console.log("x更改", windowScroll.x.value, windowScroll.y.value);
})
watch(windowScroll.y, () =>
{
  console.log("y更改", windowScroll.x.value, windowScroll.y.value);
})

</script>

<style scoped>
.div {
  text-align: center;
  width: 500vw;
  height: 2000vh;
  background: dodgerblue;
}


</style>
