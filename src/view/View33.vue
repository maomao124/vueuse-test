<template>
  <p>基于 Window.getSelection 响应式跟踪用户文本选择</p>

  <h2>{{ textSelection.text }}</h2>
  <h2>{{ textSelection.rects }}</h2>
</template>

<script lang="ts" setup>
import {computed, ref} from "vue";
import {useTextSelection} from "@vueuse/core";

const textSelection = useTextSelection();

</script>

<style scoped>

</style>
