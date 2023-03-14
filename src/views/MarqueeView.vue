<script setup lang="ts">
import Marquee from '../components/Marquee.vue'
</script>

<template>
  <main>
    <Marquee :msg="'sds'" :height="50" :width="400" />
  </main>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
