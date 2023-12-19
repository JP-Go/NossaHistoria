<script setup lang="ts">
import { onMounted, ref } from 'vue';
import TimelineItem from './TimelineItem.vue';
const timeline = ref([]);

onMounted(async () => {
  const response = await fetch('/timeline-items.json');
  const { timeline: timelineItems } = await response.json();
  timeline.value = timelineItems.map((t: any) => ({
    ...t,
    timestamp: new Date(t.timestamp),
  }));
});
</script>

<template>
  <div class="container">
    <div class="relative flex flex-col items-center gap-24 py-8">
      <div class="bg-sky-900 h-full md:w-2 w-1 z-0 absolute" />
      <TimelineItem
        v-for="(item, index) in timeline"
        :item="item"
        :key="item"
        :reverse="index % 2 === 0"
      />
    </div>
  </div>
</template>
