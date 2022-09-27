<script setup lang="ts"></script>

<template>
  <div
    class="flex flex-col items-left justify-between gap-5 py-5 md:(flex-row items-center px-5 )"
  >
    <h1 class="text-3xl font-bold">
      My name's
      <span
        class="underline underline-2 underline-offset-4 underline-indigo-500 hover:(text-indigo-500)"
        >Ahmed</span
      >
    </h1>
    <p class="text-lg">
      I'm an aspiring web developer, with skills in linux, general programming,
      and networking
    </p>

    <div class="flex flex-wrap justify-end gap-3 font-bold">
      <a
        href="https://github.com/ahmedkabd"
        class="underline underline-2 underline-transparent underline-offset-4 hover:(underline underline-2 underline-indigo-500 underline-offset-4)"
        >Github</a
      >
      <a
        href="mailto:email@ahmed.systems"
        class="underline underline-2 underline-transparent underline-offset-4 hover:(underline underline-2 underline-indigo-500 underline-offset-4)"
        >Email</a
      >
    </div>
  </div>
</template>
