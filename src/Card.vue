<script setup lang="ts">
const props = defineProps<{
  title: string;
  points: string[];
  darkMode: boolean;
}>();
</script>

<template>
  <div
    class="rounded-xl p-3 w-full bg-true-gray-200 shadow-sm shadow-true-gray-500 hover:(bg-indigo-500 text-true-gray-100 cursor-pointer)"
    :class="{ 'bg-true-gray-800 text-gray-100': darkMode }"
  >
    <h1>{{ props.title }}</h1>
    <p v-for="point in props.points">
      {{ point }}
    </p>
  </div>
</template>
