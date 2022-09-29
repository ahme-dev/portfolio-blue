<script setup lang="ts">
import { ref } from "vue";
import Card from "./Card.vue";
import { info } from "./info";

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
  <div class="app" :class="{ 'app-dark': darkMode }">
    <!-- Top  -->

    <div class="nav">
      <h1 class="title">
        My name's
        <span class="title-highlight">Ahmed</span>
      </h1>
      <p class="paragraph">
        I'm an aspiring web developer, with skills in linux, general
        programming, and networking
      </p>

      <div class="links">
        <a href="https://github.com/ahmedkabd" class="link">Github</a>
        <a href="mailto:email@ahmed.systems" class="link">Email</a>
      </div>
    </div>

    <!-- Middle -->

    <div class="cards">
      <Card
        v-for="e in info"
        :class="{ 'row-span-2': e.title == 'Projects' }"
        :title="e.title"
        :points="e.items"
        :darkMode="darkMode"
      />
    </div>

    <!-- Bottom -->

    <button class="button" @click="toggleDarkMode">
      {{ darkMode ? "Dark" : "Light" }}
    </button>
  </div>
</template>

<style scoped>
.app {
  @apply flex flex-col justify-between
  @apply p-5 gap-5 min-h-screen
  @apply bg-true-gray-100;
}
.app-dark {
  @apply bg-true-gray-900 text-true-gray-100;
}

/* Top */

.nav {
  @apply flex flex-col items-start justify-between gap-5
  @apply my-5
  @apply md:(flex-row items-center px-5);
}
.title {
  @apply text-3xl font-bold;
}
.title-highlight {
  @apply underline underline-2 underline-offset-4 underline-indigo-600
  @apply hover:(text-indigo-600);
}
.paragraph {
  @apply text-lg;
}
.links {
  @apply flex flex-wrap justify-end gap-3
  @apply font-bold;
}
.link {
  @apply underline underline-2 underline-transparent underline-offset-4
  @apply hover:(underline underline-2 underline-indigo-500 underline-offset-4);
}

/* Middle */

.cards {
  @apply grid grid-cols-1 gap-1rem
  @apply md:(grid-cols-2 px-6 gap-6)
  @apply lg:(grid-cols-3 px-8 gap-8);
}

/* Bottom */

.button {
  @apply bg-gradient-to-b from-indigo-600 to-indigo-700 text-true-gray-100
  @apply rounded-full my-5 px-5 py-3
  @apply self-center;
}
</style>
