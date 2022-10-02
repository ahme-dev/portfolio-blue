<script setup lang="ts"></script>

<template>
  <div class="version">
    <img src="https://img.icons8.com/ios-filled/50/000000/design--v1.png" />
    <a class="vlink" href="https://ahmed.systems"> A </a>
    <a class="selected" href="https://b.ahmed.systems"> B </a>
    <a class="vlink" href="https://c.ahmed.systems"> C </a>
  </div>
</template>

<style scoped>
  .version {
    font-family: sans-serif;
    position: fixed;
    bottom: 1rem;
    right: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    background-color: aliceblue;
    border: 2px solid #333;
    border-radius: 1rem;
    padding: 0.2rem 0.5rem;
  }
  .version > .vlink,
  .version > .selected {
    display: flex;
    justify-content: center;
    align-items: center;
    color: #333;
    text-decoration: none;
    border-radius: 50%;
    padding: 0.1rem 0.5rem;
  }
  .version > .selected {
    background-color: mediumslateblue;
    cursor: default;
  }
  .version > .vlink:hover {
    background-color: mediumaquamarine;
  }
  .version > img {
    width: 2rem;
    opacity: 0.9;
  }
</style>
