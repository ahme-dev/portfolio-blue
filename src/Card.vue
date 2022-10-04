<script setup lang="ts">
  const props = defineProps<{
    title: string;
    points: string[];
  }>();
</script>

<template>
  <div v-motion-slide-visible-left class="card">
    <h1 class="title">{{ props.title }}</h1>
    <div class="points">
      <p class="point" v-for="point in props.points">
        {{ point }}
      </p>
    </div>
  </div>
</template>

<style scoped>
  .card {
    @apply flex flex-col gap-4;
    @apply rounded-xl p-5 w-full;
    @apply bg-blue-gray-200 shadow-sm shadow-blue-gray-500;
    @apply dark:(bg-true-gray-800 text-blue-gray-100);
    @apply hover:( bg-gradient-to-b from-indigo-600 to-indigo-700 text-blue-gray-100 cursor-pointer);
  }
  .title {
    @apply text-2xl;
  }
  .points {
    @apply flex flex-wrap gap-2 items-stretch justify-start;
  }
  .point {
    @apply rounded-lg p-2;
    @apply bg-opacity-50 bg-blue-gray-400;
    @apply hover:(bg-indigo-200 text-blue-gray-800);
  }
</style>
