<script setup lang="ts">
import Card from "./Card.vue";
import Top from "./Top.vue";
</script>

<template>
  <div class="flex flex-col p-5 gap-5 min-h-screen">
    <Top />
    <div class="grid gap-1rem md:(grid-cols-2 p-8 gap-8)">
      <Card title="Skills" :points="['i like this', 'i like that']" />
      <Card title="Hobbies" :points="['i like this', 'i like that']" />
      <Card title="Projects" :points="['i like this', 'i like that']" />
      <Card title="Hobbies" :points="['i like this', 'i like that']" />
      <Card title="Projects" :points="['i like this', 'i like that']" />
      <Card title="Hobbies" :points="['i like this', 'i like that']" />
    </div>
  </div>
</template>
