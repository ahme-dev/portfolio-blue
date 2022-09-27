<script setup lang="ts">
import { ref } from "vue";
import Card from "./Card.vue";
import Top from "./Top.vue";
const darkMode = ref(true);
const toggleDarkMode = () => (darkMode.value = !darkMode.value);
</script>

<template>
  <div
    class="flex flex-col p-5 gap-5 min-h-screen bg-true-gray-100"
    :class="{ 'bg-true-gray-900 text-true-gray-100': darkMode }"
  >
    <Top />
    <div class="grid gap-1rem md:(grid-cols-2 p-8 gap-8)">
      <Card
        :darkMode="darkMode"
        title="Skills"
        :points="['i like this', 'i like that']"
      />
      <Card
        :darkMode="darkMode"
        title="Hobbies"
        :points="['i like this', 'i like that']"
      />
      <Card
        :darkMode="darkMode"
        title="Projects"
        :points="['i like this', 'i like that']"
      />
      <Card
        :darkMode="darkMode"
        title="Hobbies"
        :points="['i like this', 'i like that']"
      />
      <Card
        :darkMode="darkMode"
        title="Projects"
        :points="['i like this', 'i like that']"
      />
      <Card
        :darkMode="darkMode"
        title="Hobbies"
        :points="['i like this', 'i like that']"
      />
    </div>
    <button
      @click="toggleDarkMode"
      class="bg-indigo-500 text-true-gray-100 rounded-md px-4 py-2 self-center"
    >
      {{ darkMode ? "Dark" : "Light" }}
    </button>
  </div>
</template>
