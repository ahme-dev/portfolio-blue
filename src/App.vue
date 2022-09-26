<script setup lang="ts">
import Card from "./Card.vue";
import Top from "./Top.vue";
</script>

<template>
  <div class="flex flex-col items-center min-h-screen">
    <Top />
    <Card title="Skills" :points="['i like this', 'i like that']" />
  </div>
</template>
