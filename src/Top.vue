<script setup lang="ts"></script>

<template>
  <div class="top">
    <h1 class="title">
      My name's
      <span class="title-highlight">Ahmed</span>
    </h1>
    <p class="paragraph">
      I'm an aspiring web developer, with skills in linux, general programming,
      and networking
    </p>

    <div class="links">
      <a href="https://github.com/ahmedkabd" class="link">Github</a>
      <a href="mailto:email@ahmed.systems" class="link">Email</a>
    </div>
  </div>
</template>

<style>
.top {
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
</style>
