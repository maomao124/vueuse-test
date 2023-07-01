<template>
  <div>
    <div id="d" ref="target">
      <h1>Hello world</h1>
    </div>
    <h1>{{ x }},{{ y }}<br>
      {{ isOutside }}<br>
      {{ elementX }},{{ elementY }}</h1>
  </div>
</template>

<script lang="ts" setup>

import {ref} from "vue";
import {useMouseInElement} from "@vueuse/core";

const target = ref(null)
const {x, y, isOutside, elementX, elementY} = useMouseInElement(target)

</script>

<style scoped>

#d {
  background: darksalmon;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 200px;
  height: 200px;
}
</style>
