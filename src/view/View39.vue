<template>
  <h2>list:{{ list }}</h2>
  <button @click="change1">+1元素</button>
  <button @click="change2">-1元素</button>
</template>

<script lang="ts" setup>

import {watchArray} from "@vueuse/core";
import {ref} from "vue";

const list = ref([1, 2, 3])

function change1()
{
  list.value.push(Math.round(Math.random() * 100 + 10))
}

function change2()
{
  if (list.value.length > 0)
  {
    list.value.pop()
  }
}

watchArray(list, (newList, oldList, added, removed) =>
{
  console.log('新数组：', newList)
  console.log('旧数组：', oldList)
  console.log("添加的元素：", added)
  console.log("移除的元素：", removed)
}, {deep: true})


</script>

<style scoped>

</style>
