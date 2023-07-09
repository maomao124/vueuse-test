<template>
  <h2>格式化的日期:{{ formatted }}</h2>
</template>

<script lang="ts" setup>

import {useDateFormat, useNow, watchThrottled} from "@vueuse/core";
import {ref} from "vue";

const formatted = useDateFormat(useNow(), 'YYYY-MM-DD HH:mm:ss')

</script>

<style scoped>
h2 {
  color: red;
}
</style>
