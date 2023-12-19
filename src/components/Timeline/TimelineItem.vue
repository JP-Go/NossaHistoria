<script setup lang="ts">
defineProps<{
  reverse?: boolean;
  item: {
    title: string;
    description: string;
    timestamp: Date;
  };
}>();
</script>
<template>
  <div
    class="grid grid-cols-[1fr_clamp(40px,20%,300px)_1fr] place-items-center z-0 relative px-4 sm:px-0"
    :style="{ direction: reverse ? 'rtl' : 'ltr' }"
  >
    <img
      src="https://picsum.photos/400/400"
      alt="Image"
      class="rounded-md border-4 md:border-8 border-sky-900 lg:w-auto md:w-64 w-full aspect-square justify-self-end"
    />
    <div class="flex items-center justify-center relative w-full">
      <div class="w-4 h-4 md:w-6 md:h-6 rounded-full bg-sky-900 absolute" />
      <div class="w-full h-1 md:h-2 bg-sky-900 place-self-center -z-10" />
    </div>
    <div
      class="rounded-md border-4 md:border-8 border-sky-900 p-2 bg-white w-7/8 sm:max-w-[400px] justify-self-start"
    >
      <h2 class="font-bold md:text-2xl mb-2 ltr">
        {{ item.title }} ({{
          Intl.DateTimeFormat('pt-BR', {
            month: 'numeric',
            year: 'numeric',
          })
            .format(item.timestamp)
            .toString()
        }})
      </h2>
      <p class="font-light text-sm md:text-xl ltr">
        {{ item.description }}
      </p>
    </div>
  </div>
</template>
