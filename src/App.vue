<script setup lang="ts">
import Header from './components/Header/Header.vue';
import Timeline from './components/Timeline/Timeline.vue';
</script>

<template>
  <main class="bg-orange-50 w-screen">
    <Header />
    <section class="h-full pt-20 flex justify-center">
      <Timeline />
    </section>
  </main>
</template>
