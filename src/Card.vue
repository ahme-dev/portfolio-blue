<script setup lang="ts">
const props = defineProps<{
  title: string;
  points: string[];
  darkMode: boolean;
}>();
</script>

<template>
  <div
    class="flex flex-col gap-4 rounded-xl p-5 w-full bg-true-gray-200 shadow-sm shadow-true-gray-500 hover:( bg-gradient-to-b from-indigo-600 to-indigo-700 text-true-gray-100 cursor-pointer)"
    :class="{ 'bg-true-gray-800 text-true-gray-100': props.darkMode }"
  >
    <h1 class="text-2xl">{{ props.title }}</h1>

    <div class="flex flex-wrap gap-2 items-stretch justify-start">
      <p
        class="p-2 rounded-lg bg-opacity-50 bg-true-gray-400"
        v-for="point in props.points"
      >
        {{ point }}
      </p>
    </div>
  </div>
</template>

<style>
div {
}
</style>
