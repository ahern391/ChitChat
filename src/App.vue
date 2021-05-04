<template>
  <div class="main">
    <div class="title">
      <mdi:controller-classic-outline />
      <h1 class="">Hello There</h1>
    </div>
    <p class="text-xl">Mouse is on {{ x }} and {{ y }}</p>
  </div>
</template>

<script setup>
  import { useMouse } from '@vueuse/core'

  const { x, y } = useMouse()
</script>

<style lang="postcss">
  .main {
    @apply flex flex-col items-center justify-center min-h-screen space-x-4 text-6xl text-coolGray-300 font-extralight;
  }
  .title {
    @apply flex items-center justify-center;
  }
</style>
