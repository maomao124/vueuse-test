<template>
  <div>
    <button ref="el" type="button">按钮</button>
  </div>
</template>

<script setup lang="ts">
import {ref} from "vue";
import {useEventListener} from "@vueuse/core";

const el = ref<HTMLButtonElement>();
useEventListener(el, 'click', () =>
{
  alert("按钮被点击了")
})

</script>

<style scoped>

</style>
