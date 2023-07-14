<template>
  <button @click="progress.isLoading = !progress.isLoading">
    {{ !progress.isLoading ? 'Start' : 'Stop' }}
  </button>
  <b v-if="progress.isLoading">{{ ((progress.progress || 0) * 100).toFixed(0) }}%</b>
</template>

<script lang="ts" setup>
import { useNProgress } from '@vueuse/integrations/useNProgress'

const progress = useNProgress()


</script>

<style scoped>

</style>
