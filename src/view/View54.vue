<template>
  <h2>jwt头信息：:{{ header }}</h2>
  <h2>有效载荷:{{ payload }}</h2>
  <br>
  <h2>jwt头信息：:{{ useJwt2.header }}</h2>
  <h2>有效载荷:{{ useJwt2.payload }}</h2>
  <br>
  <h2>jwt头信息：:{{ useJwt3.header }}</h2>
  <h2>有效载荷:{{ useJwt3.payload }}</h2>
</template>

<script lang="ts" setup>

import {useJwt} from '@vueuse/integrations/useJwt'
import {ref} from "vue";

const encodedJwt = ref(
    //头
    'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9' +
    //有效载荷
    '.eyJzdWIiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyfQ' +
    //加密
    '.L8i6g3PfcHlioHCCPURC9pmXT7gdJpx3kOoyAfNUwCc')
const {header, payload} = useJwt(encodedJwt)

const encodedJwt2 = ref("eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9" +
    ".eyJzZXgiOiLnlLciLCJ1c2VySWQiOiIxMDAwMiIsImp0aSI6Imp3dDIiLCJ1c2VybmFtZSI6IuW8oOS4iSJ9" +
    ".9TC0U77uYueqnUdU_we2yVUZ6uj9mrsLPhjr4gB2v98")

const useJwt2 = useJwt(encodedJwt2)

const RSAToken = ref("eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9" +
    ".eyJzZXgiOiLnlLciLCJ1c2VySWQiOiIxMDAwMyIsImp0aSI6Imp3dDMiLCJ1c2VybmFtZSI6IuW8oOS4iSJ9" +
    ".Ke2o0WFNNQp71Sdd056bP2Z2CywxfaV4M9OUtsPNBmrLWSLNOkqUao3DiTdX2kLMMWjVQ4THnCQHRiJhXa2uPX6qLfNPHhCC1unYFBlU17WAPSfpp3BeEF4UK3G5GOiamLFghiowlwG84_3AuNFOj8JZXY4Beq_FpT9PSo1608M");
const useJwt3 = useJwt(RSAToken)

</script>

<style scoped>

</style>
