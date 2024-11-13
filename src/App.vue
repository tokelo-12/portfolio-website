<script setup lang="ts">
import Bubbles from './components/Bubbles.vue'
import { RouterView, RouterLink } from 'vue-router';
</script>

<template>
  <body>
    
    <RouterView/>
    <Bubbles/>
    
  </body>
</template>

<style lang="scss">
@import './assets/main.scss';
</style>


