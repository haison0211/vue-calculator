<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div class="wrapper">
    <h1>Vue Calcultor</h1>
    <RouterView />
  </div>
</template>

<style scoped>
.wrapper {
    width: 100%;
    text-align: center;
}
</style>
