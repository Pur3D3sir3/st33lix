<script setup>
import { ref } from "vue";

const show_loader = ref(true);

setTimeout(() => {
  show_loader.value = false;
}, 3000);
</script>

<template>
  <div
    class="loader simple-loader animate__animated"
    :class="{ animate__fadeOut: !show_loader }"
    v-if="show_loader"
  >
    <div class="loader-body"></div>
  </div>
</template>

<style lang="scss" scoped>
.simple-loader {
    background-color: #141414;
    height: 100%;
    width: 100%;
    position: fixed;
    place-content: center;
    overflow: hidden !important;
    right: 0;
    z-index: 1250;
}
.loader-body {
    background: url(../../assets/loader.gif) no-repeat scroll center center;
    background-size: 20%;
    width: 100%;
    height: 100%;
    position: relative;
}

</style>
