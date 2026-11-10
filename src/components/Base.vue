<template>
  <div class="baseBeverage" :style="{ backgroundColor: color }"></div>
</template>

<script setup lang="ts">
defineProps<{ color: string }>();
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  background-image: linear-gradient(
    to bottom,
    rgba(255, 255, 255, 0.15),
    rgba(0, 0, 0, 0.25)
  );
  transition: background-color 0.5s;
}
</style>
