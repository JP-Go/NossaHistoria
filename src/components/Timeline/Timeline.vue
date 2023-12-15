<script setup lang="ts">
import TimelineItem from './TimelineItem.vue';
</script>

<template>
  <div class="container">
    <div class="relative flex flex-col items-center gap-24 py-8">
      <div class="bg-sky-900 h-full md:w-2 w-1 z-0 absolute" />
      <TimelineItem reverse />
      <TimelineItem />
      <TimelineItem reverse />
      <TimelineItem />
    </div>
  </div>
</template>
