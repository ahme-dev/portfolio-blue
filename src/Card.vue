<script setup lang="ts">
const props = defineProps<{ title: string; points: string[] }>();
</script>

<template>
  <div class="bg-orange-300 p-4 md:px-20 md:w-1/2 w-full">
    <h1 class="text-3xl bold">{{ props.title }}</h1>
    <p class="text-xl" v-for="point in props.points">
      {{ point }}
    </p>
  </div>
</template>
