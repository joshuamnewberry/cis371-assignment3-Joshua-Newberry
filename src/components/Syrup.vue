<template>
  <div class="syrup" :style="{ '--syrup-color': color }"></div>
</template>

<script setup lang="ts">
defineProps<{ color: string }>();
</script>
<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
  // diagonal swirl stripes in the syrup's color
  background: repeating-linear-gradient(
    45deg,
    var(--syrup-color),
    var(--syrup-color) 10px,
    rgba(255, 255, 255, 0.6) 10px,
    rgba(255, 255, 255, 0.6) 20px
  );
  background-color: var(--syrup-color);
}
</style>
