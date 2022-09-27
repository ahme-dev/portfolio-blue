<script setup lang="ts">
const props = defineProps<{
  title: string;
  points: string[];
}>();
</script>

<template>
  <div
    class="rounded-lg p-3 w-full bg-true-gray-100 shadow-sm shadow-true-gray-400 duration-300 ease-in hover:(bg-indigo-400 text-light-200 cursor-pointer)"
  >
    <h1>{{ props.title }}</h1>
    <p v-for="point in props.points">
      {{ point }}
    </p>
  </div>
</template>
