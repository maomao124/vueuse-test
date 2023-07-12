<template>
  <h2>data1:{{ data1 }}</h2>
  <h2>data2:{{ data2 }}</h2>
</template>

<script lang="ts" setup>

import {useAxios} from '@vueuse/integrations/useAxios'
import axios from "axios";

const {data1, isFinished} = useAxios('/api/posts')

const instance = axios.create({
  baseURL: '/api',
})

const {data2} = useAxios('/posts', {method: 'POST'}, instance)

</script>

<style scoped>

</style>
