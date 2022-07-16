<script setup></script>

<template>
  <router-view />
</template>

<style lang="scss">
html, body, #app {
    height: 100%;
}

body {
    background-color: $black;
}

#app {
    font-family: Poppins, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: $white;
}

</style>
