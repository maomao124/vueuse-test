<template>
  内容：{{ text }}
  <br>
  对应二维码：
  <br>
  <img :src="qrCode" alt="QR Code"/>
  <br>
  <br>
  内容：{{ text2 }}
  <br>
  对应二维码：
  <br>
  <img :src="qrCode2" alt="QR Code"/>
  <br>
  <br>
  内容：{{ text3 }}
  <br>
  对应二维码：
  <br>
  <img :src="qrCode3" alt="QR Code"/>
  <br>
  <br>
  <button @click="text3=text3+'0'">+1长度</button>
</template>

<script lang="ts" setup>
import {useQRCode} from "@vueuse/integrations/useQRCode";
import {ref} from "vue";

const text = "hello"
const qrCode = useQRCode(text);
const text2 = "13244235354353435346346"
const qrCode2 = useQRCode(text2);

const text3 = ref("10000")
const qrCode3 = useQRCode(text3);

</script>

<style scoped>

</style>
