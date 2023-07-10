<template>
  <h2>timeAgo1:{{ timeAgo1 }}</h2>
  <h2>timeAgo2:{{ timeAgo2 }}</h2>
  <h2>timeAgo3:{{ timeAgo3 }}</h2>
  <h2>timeAgo4:{{ timeAgo4 }}</h2>
  <h2>timeAgo5:{{ timeAgo5 }}</h2>
  <h2>timeAgo6:{{ timeAgo6 }}</h2>
  <h2>今天:{{ new Date().toLocaleString() }}</h2>

</template>

<script lang="ts" setup>

import {useTimeAgo} from "@vueuse/core";
import {ref} from "vue";

const timeAgo1 = useTimeAgo(new Date(2022, 1, 1));
const timeAgo2 = useTimeAgo(new Date(2023, 6, 1));
const timeAgo3 = useTimeAgo(new Date(2017, 7, 15));
const timeAgo4 = useTimeAgo(new Date(2024, 9, 5));
const timeAgo5 = useTimeAgo(new Date(2023, 6, 9));
const timeAgo6 = useTimeAgo(new Date(2023, 6, 10));

</script>

<style scoped>
h2 {
  color: red;
}
</style>
