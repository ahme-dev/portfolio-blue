<script setup lang="ts">
import { ref } from "vue";
import Card from "./Card.vue";
import Top from "./Top.vue";

// load dark mode from localstorage
const loadDarkMode = (): boolean => {
  const darkMode = window.localStorage.getItem("darkMode");
  if (darkMode === "false") return false;
  else return true;
};

const darkMode = ref(loadDarkMode());

// switch between dark and light mode
const toggleDarkMode = () => {
  darkMode.value = !darkMode.value;

  // set value in localstorage
  window.localStorage.setItem("darkMode", darkMode.value.toString());
};
</script>

<template>
  <div
    class="flex flex-col justify-between p-5 gap-5 min-h-screen bg-true-gray-100"
    :class="{ 'bg-true-gray-900 text-true-gray-100': darkMode }"
  >
    <Top />
    <div
      class="grid grid-cols-1 gap-1rem md:(grid-cols-2 px-6 gap-6) lg:(grid-cols-3 px-8 gap-8)"
    >
      <Card
        :darkMode="darkMode"
        title="About"
        :points="[
          'In Node Group\'s bootcamp',
          'Learning MEVN stack',
          'Making small projects here and there',
        ]"
      />

      <Card
        :darkMode="darkMode"
        title="Skills"
        :points="[
          'Linux',
          'Javascript/Typescript',
          'VueJS',
          'Go',
          'C#',
          'Docker',
        ]"
      />
      <Card
        :darkMode="darkMode"
        title="Projects"
        class="row-span-2"
        :points="[
          'Centerm, cli tool in golang for modifying system settings',
          'Journalv, in development electron/vue app for day and dream journaling',
          'Hawr, react weather app in kurdish with 2 day forecasting and no features at all',
          'Gettube, windows desktop app in c# that downloads videos',
        ]"
      />
      <Card
        :darkMode="darkMode"
        title="Experience"
        :points="['Data Entry / IT Technician', 'IT Support', 'Translation']"
      />
      <Card
        :darkMode="darkMode"
        title="Education"
        :points="[
          'Diploma in Computer Networking',
          'Computer Institute of Sulaymaniah',
        ]"
      />
      <Card
        :darkMode="darkMode"
        title="Interests"
        :points="['Reading', 'Linux', 'Coding']"
      />
    </div>
    <button
      @click="toggleDarkMode"
      class="bg-gradient-to-b from-indigo-600 to-indigo-700 text-true-gray-100 rounded-full my-5 px-5 py-3 self-center"
    >
      {{ darkMode ? "Dark" : "Light" }}
    </button>
  </div>
</template>
