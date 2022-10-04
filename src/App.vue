<script setup lang="ts">
  import { ref } from "vue";
  import Card from "./Card.vue";
  import { info } from "./info";
  import Version from "./Version.vue";

  import { useDark, useToggle } from "@vueuse/core";

  const isDark = useDark();
  const toggleDark = useToggle(isDark);
</script>

<template>
  <div class="app">
    <!-- Top  -->

    <div class="nav">
      <h1 class="title">
        My name's
        <span class="title-highlight">Ahmed</span>
      </h1>
      <p class="paragraph">
        I'm an aspiring web developer, with skills in linux, programming, and
        networking
      </p>

      <div class="links">
        <a href="https://github.com/ahmedkabd" class="link">
          <img
            class="pic"
            :class="{ 'pic-dark': isDark }"
            src="https://img.icons8.com/windows/128/000000/github.png"
          />
          Github</a
        >
        <a href="mailto:email@ahmed.systems" class="link">
          <img
            class="pic"
            :class="{ 'pic-dark': isDark }"
            src="https://img.icons8.com/windows/128/000000/email.png"
          />
          Email</a
        >
      </div>
    </div>

    <!-- Middle -->

    <div class="cards">
      <Card
        v-for="e in info"
        :class="{ 'row-span-2': e.title == 'Projects' }"
        :title="e.title"
        :points="e.items"
      />
    </div>

    <!-- Bottom -->

    <button class="button" @click="toggleDark()">
      <img
        class="pic pic-dark"
        src="https://img.icons8.com/windows/100/000000/light--v1.png"
      />
      <h5>
        {{ isDark ? "Dark" : "Light" }}
      </h5>
    </button>

    <Version></Version>
  </div>
</template>

<style scoped>
  .app {
    @apply flex flex-col justify-between;
    @apply p-5 gap-5 min-h-screen;
    @apply bg-blue-gray-100;
    @apply dark:( bg-true-gray-900 text-blue-gray-100);
  }

  /* Top */

  .nav {
    @apply flex flex-col items-start justify-between gap-5;
    @apply my-5;
    @apply md:(flex-row items-center px-5);
  }
  .title {
    @apply text-3xl font-bold;
  }
  .title-highlight {
    @apply underline underline-2 underline-offset-4 underline-indigo-600;
    @apply hover:(text-indigo-600);
  }
  .paragraph {
    @apply text-base;
  }
  .links {
    @apply flex flex-wrap justify-end gap-3;
    @apply font-bold;
  }
  .link {
    @apply flex flex-row gap-2;
    @apply underline underline-2 underline-transparent underline-offset-4;
    @apply hover:(underline underline-2 underline-indigo-500 underline-offset-4);
  }

  /* Middle */

  .cards {
    @apply grid grid-cols-1 gap-4;
    @apply md:(grid-cols-2 px-6 gap-6);
    @apply lg:(grid-cols-3 px-8 gap-8);
  }

  .cards > *:hover {
    scale: 1.03;
  }

  /* Bottom */

  .button {
    @apply flex items-center gap-2;
    @apply bg-gradient-to-b from-indigo-600 to-indigo-700 text-blue-gray-100;
    @apply rounded-full my-5 px-5 py-3;
    @apply self-center;
  }

  /* pictures */
  .pic {
    @apply w-6 opacity-80;
  }
  .pic-dark {
    filter: invert(100%);
  }
</style>
